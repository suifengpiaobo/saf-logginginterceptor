# saf-logginginterceptor

[![@Tony沈哲 on weibo](https://img.shields.io/badge/weibo-%40Tony%E6%B2%88%E5%93%B2-blue.svg)](http://www.weibo.com/fengzhizi715)
[![Download](https://api.bintray.com/packages/fengzhizi715/maven/saf-logginginterceptor/images/download.svg)](https://bintray.com/fengzhizi715/maven/saf-logginginterceptor/_latestVersion)
[![License](https://img.shields.io/badge/license-Apache%202-lightgrey.svg)](https://www.apache.org/licenses/LICENSE-2.0.html)
<a href="http://www.methodscount.com/?lib=com.safframework.log%3Asaf-logginginterceptor%3A1.0.4"><img src="https://img.shields.io/badge/Methods and size-core: 157 | deps: 25898 | 30 KB-e91e63.svg"/></a>



用于记录OKHttp网络请求的日志的拦截器，它是纯Kotlin编写

```java
            OkHttpClient.Builder builder = new OkHttpClient.Builder();
            builder.writeTimeout(30 * 1000, TimeUnit.MILLISECONDS);
            builder.readTimeout(20 * 1000, TimeUnit.MILLISECONDS);
            builder.connectTimeout(15 * 1000, TimeUnit.MILLISECONDS);

            LoggingInterceptor loggingInterceptor = new LoggingInterceptor.Builder()
                    .loggable(BuildConfig.DEBUG)
                    .request()
                    .requestTag("Request")
                    .response()
                    .responseTag("Response")
                    .addHeader("version", BuildConfig.VERSION_NAME)
                    .build();

            //设置拦截器
            builder.addInterceptor(loggingInterceptor);
```