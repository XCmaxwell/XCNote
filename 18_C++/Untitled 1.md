## 文件处理



### iOS

* 写入iOS应用沙盒中：

```objective-c
		// OC、C++混编
		NSString *fullPath = [[NSHomeDirectory() stringByAppendingPathComponent:@"Documents"] stringByAppendingPathComponent:@"file.txt"];
    std::string filename = (char *)[fullPath cStringUsingEncoding:NSUTF8StringEncoding];
    std::ofstream weightOut(filename.c_str(), std::ios::binary|std::ios_base::app);
    weightOut.write((char*)frame->data, frame->length);
    weightOut.close();
```



```c++
		// 纯C++
		char buffer[256];
		strcpy(buffer,getenv("HOME"));
		strcat(buffer,"/Documents/file.txt");
		//Creates an empty file for writing
		FILE *f = fopen(buffer,"w");
		//Writing something
		fprintf(f, "%s %s %d", "Hello", "World", 2016);
		fclose(f);

```





### Android文件

* 写入SD卡中