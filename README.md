# python-schoolinfo
将含有高校信息的txt数据转换成excel表格
import xlwt #import model

fp=open("D:\\python\\test\patu\\school_infoadd.txt",'r') #txt file
lines=fp.readlines() # read txt lines

file=xlwt.Workbook(encoding='gb2312',style_compression=0) #creat excel file
sheet=file.add_sheet('data')
i=0
j=0
lenlines=len(lines)  #line numbers
while i<=lenlines-8: 
    
    line=lines[i]
    sheet.write(j,0,line)  #the first col
    #所在地
    school_locat=lines[i+1]
    schoollacat=school_locat.replace(school_locat[0:6],"")
    sheet.write(j,1,schoollacat) #the second col
    
    
    #学校网址
    school_url=lines[i+6]
    schoolurl=school_url.replace(school_url[0:5],"")
   #print(schoolurl)
    
    sheet.write(j,2,schoolurl) ##the third col
    i+=8
    j=j+1
    
file.save('school_infoadd.xls') 
print("Finish...")
