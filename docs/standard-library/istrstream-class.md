---
title: "istrstream sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- strstream/std::istrstream::rdbuf
- strstream/std::istrstream::str
dev_langs: C++
helpviewer_keywords: istrstream class
ms.assetid: c2d41c75-bd2c-4437-bd77-5939ce1b97af
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5e3e91e809980f32c839497ac13b4641bf72c8a2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="istrstream-class"></a>istrstream Sınıfı
Ayıklama öğelerinin denetleyen bir nesne ve akış arabellek sınıfının kodlanmış nesnelerden açıklar [strstreambuf](../standard-library/strstreambuf-class.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class istrstream : public istream
```  
  
## <a name="remarks"></a>Açıklamalar  
 Sınıfın bir nesnesi nesne depolar `strstreambuf`.  
  
> [!NOTE]
>  Bu sınıf kullanım dışıdır. Kullanmayı [istringstream](../standard-library/sstream-typedefs.md#istringstream) veya [wistringstream](../standard-library/sstream-typedefs.md#wistringstream) yerine.  
  
### <a name="constructors"></a>Oluşturucular  
  
|||  
|-|-|  
|[istrstream](#istrstream)|Türünde bir nesne oluşturur `istrstream`.|  
  
### <a name="member-functions"></a>Üye İşlevleri  
  
|||  
|-|-|  
|[rdbuf](#rdbuf)|Bir işaretçi akışa ilişkili döndürür `strstreambuf` nesnesi.|  
|[str](#str)|Çağrıları [Dondur](../standard-library/strstreambuf-class.md#freeze)ve ardından bir işaretçi denetimli sıranın başına döndürür.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<strstream >  
  
 **Namespace:** std  
  
##  <a name="istrstream"></a>istrstream::istrstream  
 Türünde bir nesne oluşturur `istrstream`.  
  
```
explicit istrstream(
    const char* ptr);

explicit istrstream(
    char* ptr);

istrstream(
    const char* ptr,
    streamsize count);

istrstream(
    char* ptr,
    int count);
```  
  
### <a name="parameters"></a>Parametreler  
 `count`  
 Arabelleğin uzunluğu ( `ptr`).  
  
 `ptr`  
 Arabellek başlatıldığı içeriğini.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağırarak tüm oluşturucular temel sınıfı başlatma [IStream](../standard-library/istream-typedefs.md#istream)( **sb**), burada **sb** saklı nesne sınıfının [strstreambuf](../standard-library/strstreambuf-class.md) . İlk iki oluşturucular ayrıca başlatma **sb** çağırarak `strstreambuf`(( **const** `char` \*) `ptr`, 0). Kalan iki oluşturucular yerine çağırın `strstreambuf`(( **const** `char` *) `ptr`, `count` ).  
  
##  <a name="rdbuf"></a>istrstream::rdbuf  
 Bir işaretçi akışın ilişkili strstreambuf nesnesi döndürür.  
  
```
strstreambuf *rdbuf() const
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Akış için bir işaretçi strstreambuf nesne ilişkili.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi türü işaretçinin saklı Akış Arabellek adresini döndürür [strstreambuf](../standard-library/strstreambuf-class.md).  
  
### <a name="example"></a>Örnek  
  Bkz: [strstreambuf::pcount](../standard-library/strstreambuf-class.md#pcount) kullanan bir örnek için `rdbuf`.  
  
##  <a name="str"></a>istrstream::Str  
 Çağrıları [Dondur](../standard-library/strstreambuf-class.md#freeze)ve ardından bir işaretçi denetimli sıranın başına döndürür.  
  
```
char *str();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Denetimli dizisi başına bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi döndürür [rdbuf](#rdbuf) -> [str](../standard-library/strstreambuf-class.md#str).  
  
### <a name="example"></a>Örnek  
  Bkz: [strstream::str](../standard-library/strstreambuf-class.md#str) kullanan bir örnek için **str**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [istream](../standard-library/istream-typedefs.md#istream)   
 [C++ Standart kitaplığında iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream programlama](../standard-library/iostream-programming.md)   
 [iostreams Kuralları](../standard-library/iostreams-conventions.md)



