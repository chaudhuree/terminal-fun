// create multiple files in the current directory

$files = "file1.txt", "file2.txt", "file3.txt"
foreach ($file in $files) {
New-Item -Name $file -ItemType "File"
}
------------------------
// create file inside folder


$folders = @(
"components/UserRegistration.js",
"components/CreateService.js",
"components/CreateReservation.js",
"components/UpdateReservationStatus.js",
"components/SuccessPage.js",
"components/ErrorPage.js"

)
foreach ($path in $folders) {
$folderPath = [System.IO.Path]::GetDirectoryName($path) # Get the folder path
New-Item -Path $folderPath -ItemType Directory -Force # Create the folder
New-Item -Path $path -ItemType File -Force # Create the file inside the folder
}
