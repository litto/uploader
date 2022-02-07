#  File Uploader

File Uploader Class for Files in PHP

##How to Install?

Install Using Composer or Direcly you can download from the Github Code You can install via composer by using this command:-

composer require litto/uploader:v1.0

## How it works?

When File is submitted in a form. In the save function call like this:-

           $absDirName =   dirname(dirname(__FILE__)).'/uploads';  // uploads folder where you are storing files
            $uploader   =   new Uploader($absDirName.'/');  //Initilize Class passing the uploader path
            $uploader->setExtensions(array('jpg','jpeg','png','gif')); // Restrict the Formats valid for thsi file upload
            $uploader->setSequence('page'); // You can set name sequence or you can pass the slug varibale for making seo friendly
            $uploader->setMaxSize(2); // Set size of the Uploader file in MB
            if($uploader->uploadFile("txtFile")){  // Class is uplaoding file where our file field name is txtFile
                /*
                 * File uploader successfully , now store to Db
                */
                $image      =   $uploader->getUploadName(); //getting uploaded file name
               // You can store  the file in your database
            }

