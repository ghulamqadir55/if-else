        driver.findElement(By.id("com.google.android.calculator:id/digit_5")).click();
        driver.findElement(By.id("com.google.android.calculator:id/op_add")).click();
        driver.findElement(By.id("com.google.android.calculator:id/digit_5")).click();
        driver.findElement(By.id("com.google.android.calculator:id/eq")).click();
        String Result = driver.findElement(By.id("com.google.android.calculator:id/result_final")).getText();

        System.out.println(Result);
        if (Result.equals("10")) {
            System.out.println("Pass");
        } else {
            System.out.println("Failed");
        }


        Thread.sleep(10000);
        driver.quit();
