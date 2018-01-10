---
title: "Platform::Collections::VectorIterator sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: COLLECTION/Platform::Collections::VectorIterator::VectorIterator
dev_langs: C++
helpviewer_keywords: VectorIterator Class
ms.assetid: d531cb42-27e0-48a6-bf5e-c265891a18ff
caps.latest.revision: "7"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b4dc6ca358959f6842cc16dcd2372094d5d7425b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="platformcollectionsvectoriterator-class"></a>Platform::Collections::VectorIterator sınıfı
Windows çalışma zamanı IVector arabiriminden türetilmiş nesneler için bir standart Şablon kitaplığı yineleyici sağlar.  
  
 VectorIterator olan VectorProxy türündeki öğeler depolayan bir proxy yineleyici\<T >. Ancak, proxy nesnesi neredeyse hiç kullanıcı kodu görünür olur. Daha fazla bilgi için bkz: [koleksiyonlar (C + +/ CX)](../cppcx/collections-c-cx.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <typename T>  
class VectorIterator;  
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 VectorIterator Şablon sınıfı typename.  
  
### <a name="members"></a>Üyeler  
  
### <a name="public-typedefs"></a>Genel tür tanımları  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`difference_type`|İşaretçi fark (ptrdiff_t).|  
|`iterator_category`|Rasgele erişim yineleyici kategorisini (:: std::random_access_iterator_tag).|  
|`pointer`|İç tür, Platform::Collections::Details::VectorProxy gösteren bir işaretçi\<T >, yani VectorIterator uygulaması için gerekir.|  
|`reference`|İç tür, Platform::Collections::Details::VectorProxy başvuru\<T >,, diğer bir deyişle VectorIterator uygulaması için gerekir.|  
|`value_type`|`T` Typename.|  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[VectorIterator::VectorIterator](#ctor)|VectorIterator sınıfının yeni bir örneğini başlatır.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[VectorIterator::operator işleci](#operator-minus)|Yineleyiciler arasında öğe sayısını verir geçerli yineleyici öğesinden yeni yineleyici ya da belirtilen yineleyici oluşturan geçerli yineleyici öğelerini itibaren belirli sayıda çıkarır.|  
|[VectorIterator::operator--işleci](#operator-decrement)|Geçerli VectorIterator azaltır.|  
|[VectorIterator::operator! = işleci](#operator-inequality)|Geçerli VectorIterator için belirtilen VectorIterator eşit olup olmadığını gösterir.|  
|[VectorIterator::operator * işleci](#operator-dereference)|Geçerli VectorIterator tarafından belirtilen öğenin bir başvuru alır.|  
|[VectorIterator::operator\[\]](#operator-at)|Belirtilen öteleme geçerli VectorIterator gelen olan öğe için bir başvuru alır.|  
|[VectorIterator::operator + işleci](#operator-plus)|Belirtilen öteleme öğede belirtilen VectorIterator başvuruda bulunan bir VectorIterator döndürür.|  
|[VectorIterator::operator ++ işleci](#operator-increment)|Geçerli VectorIterator artırır.|  
|[VectorIterator::operator += işleci](#operator-plus-assign)|Geçerli VectorIterator tarafından belirtilen öteleme artırır.|  
|[VectorIterator::operator < işleci](#operator-less-than)|Geçerli VectorIterator belirtilen VectorIterator değerinden olup olmadığını gösterir.|  
|[VectorIterator::operator\<= işleci](#operator-less-than-or-equals)|Geçerli VectorIterator küçük veya bu belirtilen VectorIterator eşit olup olmadığını gösterir.|  
|[VectorIterator::operator-= işleci](#operator-subtract-assign)|Belirtilen öteleme tarafından geçerli VectorIterator azaltır.|  
|[VectorIterator::operator == işleci](#operator-equality)|Geçerli VectorIterator için belirtilen VectorIterator eşit olup olmadığını gösterir.|  
|[VectorIterator::operator > işleci](#operator-greater-than)|Geçerli VectorIterator belirtilen VectorIterator büyük olup olmadığını gösterir.|  
|[VectorIterator::operator -> işleci](#operator-arrow)|Geçerli VectorIterator tarafından başvurulan öğenin adresi alır.|  
|[VectorIterator::operator > = işleci](#operator-greater-than-or-equal)|Geçerli VectorIterator belirtilen VectorIterator eşit veya daha büyük olup olmadığını gösterir.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `VectorIterator`  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** collection.h  
  
 **Namespace:** Platform::Collections  

## <a name="operator-arrow"></a>VectorIterator::operator -&gt; işleci
Geçerli VectorIterator tarafından başvurulan öğenin adresi alır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
Detail::ArrowProxy<T> operator->() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli VectorIterator tarafından başvurulan öğesinin değeri.  
  
 Bu işleç uygulanması için gerekli olan belirtilmeyen bir iç türü dönüş değeri türüdür.  
  


## <a name="operator-decrement"></a>VectorIterator::operator--işleci
Geçerli VectorIterator azaltır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
  
VectorIterator& operator--();  
VectorIterator operator--(int);  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk sözdizimi azaltır ve ardından geçerli VectorIterator döndürür. İkinci sözdizimi geçerli VectorIterator geçerli VectorIterator ve ardından azaltır bir kopyasını döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk VectorIterator sözdizimi geçerli VectorIterator önceden decrements.  
  
 İkinci sözdizimi geçerli VectorIterator sonrası decrements. `int` İkinci sözdiziminde türü değil gerçek tamsayı işleneni bir sonrası azaltma işlemi gösterir.  
  


## <a name="operator-dereference"></a>VectorIterator::operator * işleci
Geçerli VectorIterator tarafından belirtilen öğenin adresini alır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
reference operator*() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli VectorIterator tarafından belirtilen öğesi.  
  


## <a name="operator-equality"></a>VectorIterator::operator == işleci
Geçerli VectorIterator için belirtilen VectorIterator eşit olup olmadığını gösterir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
bool operator==(const VectorIterator& other) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `other`  
 Başka bir VectorIterator.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`Geçerli VectorIterator eşitse `other`; Aksi halde, `false`.  
  


## <a name="operator-greater-than"></a>VectorIterator::operator&gt; işleci
Geçerli VectorIterator belirtilen VectorIterator büyük olup olmadığını gösterir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
  
bool operator>(const VectorIterator& other) const   
```  
  
### <a name="parameters"></a>Parametreler  
 `other`  
 Başka bir VectorIterator.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`Geçerli VectorIterator büyükse `other`; Aksi halde, `false`.  
  


## <a name="operator-greater-than-or-equals"></a>VectorIterator::operator&gt;= işleci
Geçerli VectorIterator belirtilen VectorIterator eşit veya daha büyük olup olmadığını gösterir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
  
bool operator>=(const VectorIterator& other) const   
```  
  
### <a name="parameters"></a>Parametreler  
 `other`  
 Başka bir VectorIterator.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`Geçerli VectorIterator değerinden büyük veya eşit olup olmadığını `other`; Aksi halde, `false`.    


## <a name="operator-increment"></a>VectorIterator::operator ++ işleci
Geçerli VectorIterator artırır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```    
VectorIterator& operator++();  
VectorIterator operator++(int);  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk sözdizimi artırır ve geçerli VectorIterator döndürür. İkinci sözdizimi geçerli VectorIterator kopyasını döndürür ve geçerli VectorIterator artırır.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk VectorIterator sözdizimi geçerli VectorIterator önceden artırır.  
  
 İkinci sözdizimi geçerli VectorIterator sonrası artırır. `int` İkinci sözdiziminde türü değil gerçek tamsayı işleneni bir sonrası artırma işlemi gösterir.  
  


## <a name="operator-inequality"></a>VectorIterator::operator! = işleci
Geçerli VectorIterator için belirtilen VectorIterator eşit olup olmadığını gösterir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
bool operator!=(const VectorIterator& other) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `other`  
 Başka bir VectorIterator.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`Geçerli VectorIterator eşit değilse `other`; Aksi halde, `false`.  
  


## <a name="operator-less-than"></a>VectorIterator::operator&lt; işleci
Geçerli VectorIterator belirtilen VectorIterator değerinden olup olmadığını gösterir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
  
bool operator<(const VectorIterator& other) const   
```  
  
### <a name="parameters"></a>Parametreler  
 `other`  
 Başka bir VectorIterator.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`Geçerli VectorIterator ise değerinden `other`; Aksi halde, `false`.  
  


## <a name="operator-less-than-or-equals"></a>VectorIterator::operator&lt;= işleci
Geçerli VectorIterator küçük veya bu belirtilen VectorIterator eşit olup olmadığını gösterir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
  
bool operator<=(const VectorIterator& other) const   
```  
  
### <a name="parameters"></a>Parametreler  
 `other`  
 Başka bir VectorIterator.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`Geçerli VectorIterator küçük veya eşit olup olmadığını `other`; Aksi halde, `false`.  
  


## <a name="operator-minus"></a>VectorIterator::operator işleci
Yineleyiciler arasında öğe sayısını verir geçerli yineleyici öğesinden yeni yineleyici ya da belirtilen yineleyici oluşturan geçerli yineleyici öğelerini itibaren belirli sayıda çıkarır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
  
VectorIterator operator-(difference_type n) const;  
  
difference_type operator-(const VectorIterator& other) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `n`  
 Öğe sayısı.  
  
 `other`  
 Başka bir VectorIterator.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk işleci söz dizimi olan bir VectorIterator nesnesi döndüren `n` öğeleri geçerli VectorIterator küçüktür. İkinci işleci sözdizimi geçerli öğe sayısını döndürür ve `other` VectorIterator.  
  


## <a name="operator-plus-assign"></a>VectorIterator::operator += işleci
Geçerli VectorIterator tarafından belirtilen öteleme artırır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
VectorIterator& operator+=(difference_type n);  
```  
  
### <a name="parameters"></a>Parametreler  
 `n`  
 Bir tamsayı öteleme.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Güncelleştirilmiş VectorIterator.  
  


## <a name="operator-plus"></a>ectorIterator::operator + işleci
Belirtilen öteleme öğede belirtilen VectorIterator başvuruda bulunan bir VectorIterator döndürür.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
  
VectorIterator operator+(difference_type n);  
  
template <typename T>  
inline VectorIterator<T> operator+(
  ptrdiff_t n, 
  const VectorIterator<T>& i);  
  
```  
  
### <a name="parameters"></a>Parametreler  
 `T`  
 İkinci sözdizimi, VectorIterator typename.  
  
 `n`  
 Bir tamsayı öteleme.  
  
 `i`  
 İkinci sözdizimi, bir VectorIterator.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk sözdizimi, belirtilen öteleme öğede geçerli VectorIterator başvuruda bulunan bir VectorIterator.  
  
 Belirtilen öteleme öğede parametre baştan başvuruda bulunan bir VectorIterator ikinci sözdiziminde `i`.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk sözdizimi örneği  
  


## <a name="operator-minus-equals"></a>VectorIterator::operator-= işleci
Belirtilen öteleme tarafından geçerli VectorIterator azaltır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
VectorIterator& operator-=(difference_type n);  
```  
  
### <a name="parameters"></a>Parametreler  
 `n`  
 Bir tamsayı öteleme.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Güncelleştirilmiş VectorIterator.  
  


## <a name="operator-at"></a>VectorIterator::operator\[\]
Belirtilen öteleme geçerli VectorIterator gelen olan öğe için bir başvuru alır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```    
reference operator[](difference_type n) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `n`  
 Bir tamsayı öteleme.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tarafından hatalı yerleştirilen öğeyi `n` geçerli VectorIterator öğelerinden.  
  


## <a name="ctor"></a>VectorIterator::VectorIterator Oluşturucusu
VectorIterator sınıfının yeni bir örneğini başlatır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```    
VectorIterator();  
  
explicit VectorIterator(  
   Windows::Foundation::Collections::IVector<T>^ v);  
```  
  
### <a name="parameters"></a>Parametreler  
 `v`  
 Bir IVector\<T > nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk sözdizimi varsayılan oluşturucu örnektir. Bir IVector gelen VectorIterator oluşturmak için kullanılan bir açık Oluşturucu ikinci sözdizimi örnektir\<T > nesne.  
  


  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Platform Namespace](platform-namespace-c-cx.md)