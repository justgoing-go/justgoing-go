	mMockThread = new Thread(new Runnable() {
                @Override
                public void run() {
                    while (true) {
                        try {
                            Thread.sleep(500);
                            if (!hasAddTestProvider) {
                                Log.d("xqf", "针对Android6.0+系统，需要单独把程序调加到ADB模拟定位服务中");
                                continue;
                            }
                            setLocation(LocationUtil.mLatitude, LocationUtil.mLongitude);
                            Log.d("xqf", "setLocation240=latitude:" + mLatitude + "?longitude:" + mLongitude);
                        } catch (Exception e) {
                            e.printStackTrace();
                        }
                 }
                }
            });
            mMockThread.start();
