=================================================================================
BUATLAH form sederhana untuk melakukan upload file berupa gambar
==================================================================================
<!DOCTYPE html>
<html lang="en">
<head>
</head>
<body>
        <form action="upload.php" method="post" enctype="multipart/form-data">
            Select image to upload:
            <input type="file" name="images" id="images">
            <input type="submit" value="Upload Image" name="submit">
        </form>
</body>
</html>
===================================================================================
dan tampilkan gambar hasil upload
===================================================================================
<?php
$target_dir = "uploads/";
$target_file = $target_dir . basename($_FILES["images"]["name"]);
if(move_uploaded_file ($_FILES["images"]["tmp_name"],$target_file)){
    $nama_file = basename($_FILES["images"]["name"]);
    echo "berhasil upload";
}else{
    echo "gagal upload";
}
?>
<img src ="uploads/<?php echo $nama_file; ?>" alt="">
