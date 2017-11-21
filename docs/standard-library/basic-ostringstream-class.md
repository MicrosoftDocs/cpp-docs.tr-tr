---
title: "basic_ostringstream sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- sstream/std::basic_ostringstream
- sstream/std::basic_ostringstream::allocator_type
- sstream/std::basic_ostringstream::rdbuf
- sstream/std::basic_ostringstream::str
dev_langs: C++
helpviewer_keywords:
- std::basic_ostringstream [C++]
- std::basic_ostringstream [C++], allocator_type
- std::basic_ostringstream [C++], rdbuf
- std::basic_ostringstream [C++], str
ms.assetid: aea699f7-350f-432a-acca-adbae7b483fb
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 4a5d494d28872bf5e59f0c436ceb037bd36a94c3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="basicostringstream-class"></a>basic_ostringstream Sınıfı
Öğeler ekleme denetimlerini bir nesne ve kodlanmış nesneleri bir sınıf akışı arabelleğe açıklar [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem**, **Tr**, `Alloc`>.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <class Elem, class Tr = char_traits<Elem>, class Alloc = allocator<Elem>>  
class basic_ostringstream : public basic_ostream<Elem, Tr>  
```  
  
#### <a name="parameters"></a>Parametreler  
 `Alloc`  
 Ayırıcı sınıf.  
  
 `Elem`  
 Dizenin temel öğe türü.  
  
 *Tr*  
 Karakter nitelikler dize temel öğede özelleştirilmiş.  
  
## <a name="remarks"></a>Açıklamalar  
 Sınıf türündeki öğeler ile Akış Arabellek içine ekleme öğelerinin denetleyen bir nesne ve kodlanmış nesneleri açıklar **Elem**, olan karakter nitelikler sınıfı tarafından belirlenir **Tr**ve, öğeleri bir sınıf ayırıcı tarafından ayrılan `Alloc`. Nesne sınıfı basic_stringbuf bir nesne depolar < **Elem**, **Tr**, `Alloc`>.  
  
### <a name="constructors"></a>Oluşturucular  
  
|||  
|-|-|  
|[basic_ostringstream](#basic_ostringstream)|Türünde bir nesne oluşturur `basic_ostringstream`.|  
  
### <a name="typedefs"></a>Tür tanımları  
  
|||  
|-|-|  
|[allocator_type](#allocator_type)|Şablon parametresi için bir eş anlamlı türüdür `Alloc`.|  
  
### <a name="member-functions"></a>Üye İşlevleri  
  
|||  
|-|-|  
|[rdbuf](#rdbuf)|Tür saklı Akış Arabellek adresini döndürür `pointer` için [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< `Elem`, `Tr`, `Alloc`>.|  
|[str](#str)|Yazma konumunu değiştirmeden dize arabellekte metni alır veya ayarlar.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<sstream >  
  
 **Namespace:** std  
  
##  <a name="allocator_type"></a>basic_ostringstream::allocator_type  
 Şablon parametresi için bir eş anlamlı türüdür `Alloc`.  
  
```  
typedef Alloc allocator_type;  
```  
  
##  <a name="basic_ostringstream"></a>basic_ostringstream::basic_ostringstream  
 Bir nesne türü basic_ostringstream oluşturur.  
  
```  
explicit basic_ostringstream(ios_base::openmode _Mode = ios_base::out);

explicit basic_ostringstream(const basic_string<Elem, Tr, Alloc>& str, ios_base::openmode _Mode = ios_base::out);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Mode`  
 Numaralandırmalardan biri [ios_base::openmode](../standard-library/ios-base-class.md#openmode).  
  
 `str`  
 Türünde bir nesne `basic_string`.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk Oluşturucu çağırarak temel sınıfı başlatır [basic_ostream](../standard-library/basic-ostream-class.md)( **sb**), burada **sb** saklı nesne sınıfının [basic_stringbuf](../standard-library/basic-stringbuf-class.md) <  **Elem**, **Tr**, `Alloc`>. Ayrıca başlatır **sb** arama basic_stringbuf tarafından < **Elem**, **Tr**, `Alloc`> ( `_Mode` &#124; `ios_base::out`).  
  
 İkinci Oluşturucu, arama basic_ostream tarafından temel sınıfı başlatır ( **sb**). Ayrıca başlatır **sb** arama basic_stringbuf tarafından < **Elem**, **Tr**, `Alloc`> (_ *Str*, `_Mode` &#124; `ios_base::out`).  
  
##  <a name="rdbuf"></a>basic_ostringstream::rdbuf  
 Tür saklı Akış Arabellek adresini döndürür **işaretçi** için [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem**, **Tr**, `Alloc`>.  
  
```  
basic_stringbuf<Elem, Tr, Alloc> *rdbuf() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Adres türü saklı Akış Arabellek **işaretçi** basic_stringbuf için < **Elem**, **Tr**, `Alloc`>.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi türü saklı Akış Arabellek adresini döndürür **işaretçi** basic_stringbuf için < **Elem**, **Tr**, `Alloc`>.  
  
### <a name="example"></a>Örnek  
  Bkz: [basic_filebuf::close](../standard-library/basic-filebuf-class.md#close) kullanan bir örnek `rdbuf`.  
  
##  <a name="str"></a>basic_ostringstream::Str  
 Yazma konumunu değiştirmeden dize arabellekte metni alır veya ayarlar.  
  
```  
basic_string<Elem, Tr, Alloc> str() const;

 
void str(
    const basic_string<Elem, Tr, Alloc>& _Newstr);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Newstr`  
 Yeni bir dize.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sınıfın bir nesnesi döndüren [basic_string](../standard-library/basic-string-class.md)< **Elem**, **Tr**, `Alloc`>, yalnızca denetlenen sırasıdır denetlediği dizisinin bir kopyasını oluşturur  **\*bu**.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk üye işlevinin döndürdüğü [rdbuf](#rdbuf) -> [str](../standard-library/basic-stringbuf-class.md#str). İkinci üye işlev çağrılarını `rdbuf`  ->  **str**( `_Newstr`).  
  
### <a name="example"></a>Örnek  
  Bkz: [basic_stringbuf::str](../standard-library/basic-stringbuf-class.md#str) kullanan bir örnek **str**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Standart kitaplığında iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream programlama](../standard-library/iostream-programming.md)   
 [iostreams kuralları](../standard-library/iostreams-conventions.md)

