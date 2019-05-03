# AndroidHashGenerator
Hash generator for android apps

to use this copy and paste this code into your MainActivity

AppSignatureHelper appSignatureHelper = new AppSignatureHelper(this);
        ArrayList<String> code = appSignatureHelper.getAppSignatures();
        for (String s : code){
            Log.d("hash",s);
        }
