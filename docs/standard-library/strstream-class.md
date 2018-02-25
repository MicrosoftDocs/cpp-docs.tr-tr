---
title: "strstream sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- strstream/std::strstream::freeze
- strstream/std::strstream::pcount
- strstream/std::strstream::rdbuf
- strstream/std::strstream::str
dev_langs:
- C++
helpviewer_keywords:
- std::strstream [C++], freeze
- std::strstream [C++], pcount
- std::strstream [C++], rdbuf
- std::strstream [C++], str
ms.assetid: 63f3be31-9e36-42b1-9715-a474a5997e2a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b6b8bef6b9ae2f4000adf620e2f898113b565f2a
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="strstream-class"></a>strstream Sınıfı
Ekleme ve çıkarma öğelerinin denetleyen bir nesne sınıfının bir Akış Arabellek kullanarak ve kodlanmış nesneleri açıklar [strstreambuf](../standard-library/strstreambuf-class.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class strstream : public iostream
```  
  
## <a name="remarks"></a>Açıklamalar  
 Sınıfın bir nesnesi nesne depolar `strstreambuf`.  
  
> [!NOTE]
>  Bu sınıf kullanım dışıdır. Kullanmayı [stringstream](../standard-library/sstream-typedefs.md#stringstream) veya [wstringstream](../standard-library/sstream-typedefs.md#wstringstream) yerine.  
  
### <a name="constructors"></a>Oluşturucular  
  
|||  
|-|-|  
|[strstream](#strstream)|Türünde bir nesne oluşturur `strstream`.|  
  
### <a name="member-functions"></a>Üye İşlevleri  
  
|||  
|-|-|  
|[freeze](#freeze)|Bir Akış Arabellek Akış Arabellek işlemleri kullanılamaz hale gelmesine neden olur.|  
|[pcount](#pcount)|Denetimli sıraya yazılan öğeleri sayısını döndürür.|  
|[rdbuf](#rdbuf)|Bir işaretçi akışa ilişkili döndürür `strstreambuf` nesnesi.|  
|[str](#str)|Çağrıları [Dondur](../standard-library/strstreambuf-class.md#freeze)ve ardından bir işaretçi denetimli sıranın başına döndürür.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<strstream >  
  
 **Namespace:** std  
  
##  <a name="freeze"></a>  strstream::Freeze  
 Bir Akış Arabellek Akış Arabellek işlemleri kullanılamaz hale gelmesine neden olur.  
  
```
void freeze(bool _Freezeit = true);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Freezeit`  
 A `bool` donabilir akış isteyip istemediğinizi belirten.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlev çağrılarını [rdbuf](#rdbuf) -> [Dondur](../standard-library/strstreambuf-class.md#freeze)(_ *Freezeit*).  
  
### <a name="example"></a>Örnek  
  Bkz: [strstreambuf::freeze](../standard-library/strstreambuf-class.md#freeze) kullanan bir örnek **Dondur**.  
  
##  <a name="pcount"></a>  strstream::pcount  
 Denetimli sıraya yazılan öğeleri sayısını döndürür.  
  
```
streamsize pcount() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Denetimli sıraya yazılan öğe sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi döndürür [rdbuf](#rdbuf) -> [pcount](../standard-library/strstreambuf-class.md#pcount).  
  
### <a name="example"></a>Örnek  
  Bkz: [strstreambuf::pcount](../standard-library/strstreambuf-class.md#pcount) pcount kullanmanın bir örneği için.  
  
##  <a name="rdbuf"></a>  strstream::rdbuf  
 Bir işaretçi akışın ilişkili strstreambuf nesnesi döndürür.  
  
```
strstreambuf *rdbuf() const
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Akış için bir işaretçi strstreambuf nesne ilişkili.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi türü saklı Akış Arabellek adresini döndürür **işaretçi** için [strstreambuf](../standard-library/strstreambuf-class.md).  
  
### <a name="example"></a>Örnek  
  Bkz: [strstreambuf::pcount](../standard-library/strstreambuf-class.md#pcount) kullanan bir örnek için `rdbuf`.  
  
##  <a name="str"></a>  strstream::Str  
 Çağrıları [Dondur](../standard-library/strstreambuf-class.md#freeze)ve ardından bir işaretçi denetimli sıranın başına döndürür.  
  
```
char *str();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Denetimli dizisi başına bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi döndürür [rdbuf](#rdbuf) -> [str](../standard-library/strstreambuf-class.md#str).  
  
### <a name="example"></a>Örnek  
  Bkz: [strstreambuf::str](../standard-library/strstreambuf-class.md#str) kullanan bir örnek için **str**.  
  
##  <a name="strstream"></a>  strstream::strstream  
 Türünde bir nesne oluşturur `strstream`.  
  
```
strstream();

strstream(char* ptr,
    streamsize count,
    ios_base::openmode _Mode = ios_base::in | ios_base::out);
```  
  
### <a name="parameters"></a>Parametreler  
 `count`  
 Arabellek boyutu.  
  
 `_Mode`  
 Giriş ve çıkış modu arabellek. Bkz: [ios_base::openmode](../standard-library/ios-base-class.md#openmode) daha fazla bilgi için.  
  
 `ptr`  
 Arabellek.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağırarak temel sınıfını hem oluşturucular başlatmak [streambuf](../standard-library/streambuf-typedefs.md#streambuf)( **sb**), burada **sb** saklı nesne sınıfının [strstreambuf](../standard-library/strstreambuf-class.md) . İlk Oluşturucu ayrıca başlatır **sb** çağırarak [strstreambuf](../standard-library/strstreambuf-class.md#strstreambuf). İkinci Oluşturucu, temel sınıf iki yoldan biriyle başlatır:  
  
-   Varsa `_Mode`  &  **ios_base::app**0, ardından == `ptr` dizisinin ilk öğesi belirlemelisiniz `count` öğeleri ve oluşturucu çağrıları `strstreambuf`( `ptr`, `count`, `ptr`).  
  
-   Aksi takdirde, `ptr` dizisinin ilk öğesi, ilk öğe olarak tasarlanmış bir C dize içeren bir sayım öğelerinin belirlemelisiniz `ptr`ve oluşturucu çağrıları `strstreambuf`( `ptr`, `count`, `ptr` + `strlen`( `ptr`) ).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [iostream](../standard-library/istream-typedefs.md#iostream)   
 [C++ Standart kitaplığında iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream programlama](../standard-library/iostream-programming.md)   
 [iostreams Kuralları](../standard-library/iostreams-conventions.md)



