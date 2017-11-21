---
title: "basic_fstream sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- fstream/std::basic_fstream
- fstream/std::basic_fstream::close
- fstream/std::basic_fstream::is_open
- fstream/std::basic_fstream::open
- fstream/std::basic_fstream::rdbuf
- fstream/std::basic_fstream::swap
dev_langs: C++
helpviewer_keywords:
- std::basic_fstream [C++]
- std::basic_fstream [C++], close
- std::basic_fstream [C++], is_open
- std::basic_fstream [C++], open
- std::basic_fstream [C++], rdbuf
- std::basic_fstream [C++], swap
ms.assetid: 8473817e-42a4-430b-82b8-b476c86bcf8a
caps.latest.revision: "24"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 9f4c174050d2280f116f41be94741dc3c71ae91a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="basicfstream-class"></a>basic_fstream Sınıfı
Ekleme ve çıkarma öğelerinin denetleyen bir nesne sınıfının bir Akış Arabellek kullanarak ve kodlanmış nesneleri açıklar [basic_filebuf](../standard-library/basic-filebuf-class.md)< `Elem`, `Tr`>, türündekiöğelerile`Elem`, olan karakter nitelikler sınıfı tarafından belirlenir `Tr`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <class Elem, class Tr = char_traits<Elem>>  
class basic_fstream : public basic_iostream<Elem, Tr>  
```  
  
#### <a name="parameters"></a>Parametreler  
 `Elem`  
 Dosya arabellek temel öğesidir.  
  
 `Tr`  
 Dosya arabellek temel öğesi olarak nitelikler (genellikle `char_traits` <  `Elem`>).  
  
## <a name="remarks"></a>Açıklamalar  
 Sınıfın bir nesnesi nesne depolar `basic_filebuf` <  `Elem`, `Tr`>.  
  
> [!NOTE]
>  Get işaretçi ve put işaretçi fstream nesnenin **değil** birbirine bağımsızdır. Bu nedenle get işaretçi geçerse, put işaretçi yapar.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl oluşturulduğunu gösteren bir `basic_fstream` okuma ve yazılan nesnesi.  
  
```  
// basic_fstream_class.cpp  
// compile with: /EHsc  
  
#include <fstream>  
#include <iostream>  
  
using namespace std;  
  
int main(int argc, char **argv)  
{  
    fstream fs("fstream.txt", ios::in | ios::out | ios::trunc);  
    if (!fs.bad())  
    {  
        // Write to the file.  
        fs << "Writing to a basic_fstream object..." << endl;  
        fs.close();  
  
        // Dump the contents of the file to cout.  
        fs.open("fstream.txt", ios::in);  
        cout << fs.rdbuf();  
        fs.close();  
    }  
}  
```  
  
```Output  
Writing to a basic_fstream object...  
```  
  
### <a name="constructors"></a>Oluşturucular  
  
|||  
|-|-|  
|[basic_fstream](#basic_fstream)|Türünde bir nesne oluşturur `basic_fstream`.|  
  
### <a name="member-functions"></a>Üye İşlevleri  
  
|||  
|-|-|  
|[Kapat](#close)|Bir dosyayı kapatır.|  
|[is_open](#is_open)|Bir dosyanın açık olup olmadığını belirler.|  
|[açın](#open)|Bir dosyayı açar.|  
|[rdbuf](#rdbuf)|Saklı Akış Arabellek türü işaretçinin adresini döndürür [basic_filebuf](../standard-library/basic-filebuf-class.md)< `Elem`, `Tr`>.|  
|[değiştirme](#swap)|Bu nesne içeriği başka bir içerikle alış verişleri `basic_fstream` nesnesi.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<fstream >  
  
 **Namespace:** std  
  
##  <a name="basic_fstream"></a>basic_fstream::basic_fstream  
 Türünde bir nesne oluşturur `basic_fstream`.  
  
```  
basic_fstream();

explicit basic_fstream(
    const char* _Filename,  
    ios_base::openmode _Mode = ios_base::in | ios_base::out,  
    int _Prot = (int)ios_base::_Openprot);

explicit basic_fstream(
    const wchar_t* _Filename,  
    ios_base::openmode _Mode = ios_base::in | ios_base::out,  
    int _Prot = (int)ios_base::_Openprot);

basic_fstream(basic_fstream&& right);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Filename`  
 Açılacak dosyanın adı.  
  
 `_Mode`  
 Numaralandırmalardan biri [ios_base::openmode](../standard-library/ios-base-class.md#openmode).  
  
 `_Prot`  
 Koruma, eşdeğer açma varsayılan dosya `shflag` parametresinde [_fsopen, _wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md).  
  
### <a name="remarks"></a>Açıklamalar  
 İlk Oluşturucu çağırarak temel sınıfı başlatır [basic_iostream](../standard-library/basic-iostream-class.md)( **sb**), burada **sb** saklı nesne sınıfının [basic_filebuf](../standard-library/basic-filebuf-class.md) \< **Elem**, **Tr**>. Ayrıca başlatır **sb** çağırarak `basic_filebuf` \< **Elem**, **Tr**>.  
  
 İkinci ve üçüncü oluşturucular çağırarak temel sınıfı başlatır `basic_iostream`( **sb**). Ayrıca başlatır **sb** çağırarak `basic_filebuf` \< **Elem**, **Tr**>, ardından **sb.** [ Açık](../standard-library/basic-filebuf-class.md#open)(_ *Filename*, `_Mode`). İkinci işlevi null işaretçi döndürürse, oluşturucuyu çağırır [setstate](../standard-library/basic-ios-class.md#setstate)( **failbit**).  
  
 Dördüncü Oluşturucu içeriğini nesnesiyle başlatır `right`, rvalue başvuru olarak işlem görür.  
  
### <a name="example"></a>Örnek  
  Bkz: [streampos](../standard-library/ios-typedefs.md#streampos) kullanan bir örnek `basic_fstream`.  
  
##  <a name="close"></a>basic_fstream::Close  
 Bir dosyayı kapatır.  
  
```  
void close();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlev çağrılarını [rdbuf](#rdbuf)  **->**  [kapatmak](../standard-library/basic-filebuf-class.md#close).  
  
### <a name="example"></a>Örnek  
  Bkz: [basic_filebuf::close](../standard-library/basic-filebuf-class.md#close) nasıl kullanılacağına ilişkin bir örnek **kapatmak**.  
  
##  <a name="is_open"></a>basic_fstream::is_open  
 Bir dosyanın açık olup olmadığını belirler.  
  
```  
bool is_open() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 **doğru** dosya açıksa **false** Aksi takdirde.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi döndürür [rdbuf](#rdbuf)**->**[is_open](../standard-library/basic-filebuf-class.md#is_open).  
  
### <a name="example"></a>Örnek  
  Bkz: [basic_filebuf::is_open](../standard-library/basic-filebuf-class.md#is_open) nasıl kullanılacağına ilişkin bir örnek `is_open`.  
  
##  <a name="open"></a>basic_fstream::Open  
 Bir dosyayı açar.  
  
```  
void open(
    const char* _Filename,  
    ios_base::openmode _Mode = ios_base::in | ios_base::out,  
    int _Prot = (int)ios_base::_Openprot);

void open(
    const char* _Filename,  
    ios_base::openmode _Mode);

void open(
    const wchar_t* _Filename,  
    ios_base::openmode _Mode = ios_base::in | ios_base::out,  
    int _Prot = (int)ios_base::_Openprot);

void open(
    const wchar_t* _Filename,  
    ios_base::openmode _Mode);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Filename`  
 Açılacak dosyanın adı.  
  
 `_Mode`  
 Numaralandırmalardan biri [ios_base::openmode](../standard-library/ios-base-class.md#openmode).  
  
 `_Prot`  
 Koruma, eşdeğer açma varsayılan dosya `shflag` parametresinde [_fsopen, _wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md).  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlev çağrılarını [rdbuf](#rdbuf)  **->**  [açmak](../standard-library/basic-filebuf-class.md#open)(_ *Filename*, `_Mode`). Bu işlev bir null işaretçinin döndürürse, işlev çağrıları [setstate](../standard-library/basic-ios-class.md#setstate)( **failbit**).  
  
### <a name="example"></a>Örnek  
  Bkz: [basic_filebuf::open](../standard-library/basic-filebuf-class.md#open) nasıl kullanılacağına ilişkin bir örnek **açmak**.  
  
##  <a name="op_eq"></a>basic_fstream::operator =  
 Bu nesne için bir belirtilen stream nesnesi içerik atar. Bir kopyasını bırakmaz arkasındaki bir rvalue içerir taşıma atama budur.  
  
```  
basic_fstream& operator=(basic_fstream&& right);
```  
  
### <a name="parameters"></a>Parametreler  
 `right`  
 Lvalue başvuru için bir `basic_fstream` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `*this`.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işleci içeriğini kullanarak nesne içeriğini değiştirir `right`, rvalue başvuru olarak işlem görür.  
  
##  <a name="rdbuf"></a>basic_fstream::rdbuf  
 Saklı Akış Arabellek türü işaretçinin adresini döndürür [basic_filebuf](../standard-library/basic-filebuf-class.md) \< **Elem**, **Tr**>.  
  
```  
basic_filebuf<Elem, Tr> *rdbuf() const 
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Saklı Akış Arabellek adresi.  
  
### <a name="example"></a>Örnek  
  Bkz: [basic_filebuf::close](../standard-library/basic-filebuf-class.md#close) nasıl kullanılacağına ilişkin bir örnek `rdbuf`.  
  
##  <a name="swap"></a>basic_fstream::Swap  
 İki içeriğini alış verişleri `basic_fstream` nesneleri.  
  
```  
void swap(basic_fstream& right);
```  
  
### <a name="parameters"></a>Parametreler  
 `right`  
 Bir `lvalue` başvuru bir `basic_fstream` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu nesne içeriğini ve içeriğini üye fonksiyonu alış verişleri `right`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Standart kitaplığında iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream programlama](../standard-library/iostream-programming.md)   
 [iostreams kuralları](../standard-library/iostreams-conventions.md)

