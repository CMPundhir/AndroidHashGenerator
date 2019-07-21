# AndroidHashGenerator
Hash generator for android apps

to use this copy and paste this code into your MainActivity

AppSignatureHelper appSignatureHelper = new AppSignatureHelper(this);
        ArrayList<String> code = appSignatureHelper.getAppSignatures();
        for (String s : code){
            Log.d("hash",s);
        }



//TO generate 28 char Hash key just use below code directly , by you need to change your app apackage name with "your.package"
        try {
            PackageInfo info = getPackageManager().getPackageInfo(
                    "your.package",
                    PackageManager.GET_SIGNATURES);
            for (Signature signature : info.signatures) {
                MessageDigest md = MessageDigest.getInstance("SHA");
                md.update(signature.toByteArray());
                Log.d("KeyHash:", Base64.encodeToString(md.digest(), Base64.DEFAULT));
            }
        } catch (PackageManager.NameNotFoundException e) {
            Log.d("errorrr",e.getMessage());
        } catch (NoSuchAlgorithmException e) {
            Log.d("errorrr",e.getMessage());
        }
