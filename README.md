# 结合Glide实现很炫的图片效果框架
开源项目地址:[https://github.com/open-android/Glide-transformations](https://github.com/open-android/Glide-transformations)

 PS：如果觉得文章太长，你也可观看该课程的[视频](https://www.boxuegu.com/web/html/video.html?courseId=172&sectionId=8a2c9bed5a3a4c7e015a3bbffc6107ed&chapterId=8a2c9bed5a3a4c7e015a3b0c9441077a&vId=8a2c9bed5a3a4c7e015a3b03f3bd04da&videoId=13CAE14707B5911C9C33DC5901307461)，亲，里面还有高清，无码的福利喔

# 运行效果
  <img src="art/demo.gif" width="50%">
  
 * 爱生活,爱学习,更爱做代码的搬运工,分类查找更方便请下载黑马助手app


![黑马助手.png](http://upload-images.jianshu.io/upload_images/4037105-f777f1214328dcc4.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## 使用步骤
### 1. 在project的build.gradle添加如下代码(如下图)

	allprojects {
	    repositories {
	        ...
	        maven { url "https://jitpack.io" }
	    }
	}
  
### 2. 在Module的build.gradle添加依赖

    compile 'com.github.open-android:Glide-transformations:0.1.0'
### 3. 使用Picasso加载图片时添加显示效果

	   Glide.with(context) 
        .load(url) 
	 .transform(new CropCircleTransformation())//图片最终会展示出圆形区域
        .into(view);
	Glide-transformations 是通过Glide加载图片中通过上面的transform可以设置图片展示的效果  CropCircleTransformation是圆形效果，还有很多其他的效果
	
	模糊效果
	Glide.with(this)
	.load(R.mipmap.ic_image_sample)
        .bitmapTransform(new BlurTransformation(this))
        .into(mResultIv);
	
	圆角效果
	Glide.with(this).load(R.mipmap.ic_image_sample)
        .bitmapTransform(new RoundedCornersTransformation(this, 24, 0, 
            RoundedCornersTransformation.CornerType.ALL))
        .into(mResultIv);
	
	遮盖效果
	Glide.with(this).load(R.mipmap.ic_image_sample)
        .bitmapTransform(new MaskTransformation(this, R.mipmap.ic_launcher))
        .into(mResultIv);
	
	灰度效果
	Glide.with(this).load(R.mipmap.ic_image_sample)
        .bitmapTransform(new GrayscaleTransformation(this))
        .into(mResultIv);

	其他效果
	ToonFilterTransformation
	SepiaFilterTransformation
	ContrastFilterTransformation
	InvertFilterTransformation
	PixelationFilterTransformation
	SketchFilterTransformation
	SwirlFilterTransformation
	BrightnessFilterTransformation
	KuwaharaFilterTransformation
	VignetteFilterTransformation


* 详细的使用方法在DEMO里面都演示啦,如果你觉得这个库还不错,请赏我一颗star吧~~~

* 欢迎关注微信公众号

![](http://upload-images.jianshu.io/upload_images/4037105-8f737b5104dd0b5d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
