---
title: "Platform::Collections::VectorViewIterator sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: COLLECTION/Platform::Collections::VectorViewIterator::VectorViewIterator
dev_langs: C++
helpviewer_keywords: VectorViewIterator Class
ms.assetid: be3aa1ae-e6ba-4a06-8d6b-86d8128026f7
caps.latest.revision: "6"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b572d829c21c37457fc9fdab5f745616a6318ff1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="platformcollectionsvectorviewiterator-class"></a>Platform::Collections::VectorViewIterator sınıfı
Windows çalışma zamanı türetilen nesneler için bir standart Şablon kitaplığı yineleyici sağlar`IVectorView` arabirimi.  
  
 `ViewVectorIterator`türündeki öğeler depolayan bir proxy yineleyici olduğu `VectorProxy<T>`. Ancak, proxy nesnesi neredeyse hiç kullanıcı kodu görünür olur. Daha fazla bilgi için bkz: [koleksiyonlar (C + +/ CX)](../cppcx/collections-c-cx.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <typename T>  
class VectorViewIterator;  
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 VectorViewIterator Şablon sınıfı typename.  
  
### <a name="members"></a>Üyeler  
  
### <a name="public-typedefs"></a>Genel tür tanımları  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`difference_type`|İşaretçi fark (ptrdiff_t).|  
|`iterator_category`|Rasgele erişim yineleyici kategorisini (:: std::random_access_iterator_tag).|  
|`pointer`|VectorViewIterator uygulanması için gerekli olan iç tür için bir işaretçi.|  
|`reference`|VectorViewIterator uygulanması için gerekli olan iç tür referansı.|  
|`value_type`|`T` Typename.|  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[VectorViewIterator::VectorViewIterator](#ctor)|VectorViewIterator sınıfının yeni bir örneğini başlatır.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[VectorViewIterator::operator işleci](#operator-minus)|Yineleyiciler arasında öğe sayısını verir geçerli yineleyici öğesinden yeni yineleyici ya da belirtilen yineleyici oluşturan geçerli yineleyici öğelerini itibaren belirli sayıda çıkarır.|  
|[VectorViewIterator::operator--işleci](#operator-decrement)|Geçerli VectorViewIterator azaltır.|  
|[VectorViewIterator::operator! = işleci](#operator-inequality)|Geçerli VectorViewIterator için belirtilen VectorViewIterator eşit olup olmadığını gösterir.|  
|[VectorViewIterator::operator * işleci](#operator-dereference)|Geçerli VectorViewIterator tarafından belirtilen öğenin bir başvuru alır.|  
|[VectorViewIterator::operator\[\]](#operator-at)|Belirtilen öteleme geçerli VectorViewIterator gelen olan öğe için bir başvuru alır.|  
|[VectorViewIterator::operator + işleci](#operator-plus)|Belirtilen öteleme öğede belirtilen VectorViewIterator başvuruda bulunan bir VectorViewIterator döndürür.|  
|[VectorViewIterator::operator ++ işleci](#operator-increment)|Geçerli VectorViewIterator artırır.|  
|[VectorViewIterator::operator += işleci](#operator-plus-assign)|Geçerli VectorViewIterator tarafından belirtilen öteleme artırır.|  
|[VectorViewIterator::operator < işleci](#operator-less-than)|Geçerli VectorViewIterator belirtilen VectorViewIterator değerinden olup olmadığını gösterir.|  
|[VectorViewIterator::operator\<= işleci](#operator-less-than-or-equals)|Geçerli VectorViewIterator küçük veya bu belirtilen VectorViewIterator eşit olup olmadığını gösterir.|  
|[VectorViewIterator::operator-= işleci](#operator-minus-assign)|Belirtilen öteleme tarafından geçerli VectorViewIterator azaltır.|  
|[VectorViewIterator::operator == işleci](#operator-equality)|Geçerli VectorViewIterator için belirtilen VectorViewIterator eşit olup olmadığını gösterir.|  
|[VectorViewIterator::operator > işleci](#operator-greater-than)|Geçerli VectorViewIterator belirtilen VectorViewIterator büyük olup olmadığını gösterir.|  
|[VectorViewIterator::operator -> işleci](#operator-arrow)|Geçerli VectorViewIterator tarafından başvurulan öğenin adresi alır.|  
|[VectorViewIterator::operator > = işleci](#operator-greater-than-or-equals)|Geçerli VectorViewIterator belirtilen VectorViewIterator eşit veya daha büyük olup olmadığını gösterir.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `VectorViewIterator`  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** collection.h  
  
 **Namespace:** Platform::Collections  

## <a name="operator-arrow"></a>VectorViewIterator::operator -&gt; işleci
Geçerli VectorViewIterator tarafından başvurulan öğenin adresi alır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
Detail::ArrowProxy<T> operator->() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli VectorViewIterator tarafından başvurulan öğesinin değeri.  
  
 Bu işleç uygulanması için gerekli olan belirtilmeyen bir iç türü dönüş değeri türüdür.  
  


## <a name="operator-decrement"></a>VectorViewIterator::operator--işleci
Geçerli VectorViewIterator azaltır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
VectorViewIterator& operator--();  
VectorViewIterator operator--(int);  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk sözdizimi azaltır ve ardından geçerli VectorViewIterator döndürür. İkinci sözdizimi geçerli VectorViewIterator geçerli VectorViewIterator ve ardından azaltır bir kopyasını döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk VectorViewIterator sözdizimi geçerli VectorViewIterator önceden decrements.  
  
 İkinci sözdizimi geçerli VectorViewIterator sonrası decrements. `int` İkinci sözdiziminde türü değil gerçek tamsayı işleneni bir sonrası azaltma işlemi gösterir.  
  


## <a name="operator-dereference"></a>VectorViewIterator::operator * işleci
Geçerli VectorViewIterator tarafından belirtilen öğenin bir başvuru alır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
reference operator*() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli VectorViewIterator tarafından belirtilen öğesi.  
  


## <a name="operator-equality"></a>VectorViewIterator::operator == işleci
Geçerli VectorViewIterator için belirtilen VectorViewIterator eşit olup olmadığını gösterir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
bool operator==(const VectorViewIterator& other) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `other`  
 Başka bir VectorViewIterator.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`Geçerli VectorViewIterator eşitse `other`; Aksi halde, `false`.  
  


## <a name="operator-greater-than"></a>VectorViewIterator::operator&gt; işleci
Geçerli VectorViewIterator belirtilen VectorViewIterator büyük olup olmadığını gösterir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
  
bool operator>(const VectorViewIterator& other) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `other`  
 Başka bir VectorViewIterator.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`Geçerli VectorViewIterator büyükse `other`; Aksi halde, `false`.  
  


## <a name="operator-greater-than-or-equals"></a>VectorViewIterator::operator&gt;= işleci
Geçerli VectorViewIterator belirtilen VectorViewIterator eşit veya daha büyük olup olmadığını gösterir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
  
bool operator>=(const VectorViewIterator& other) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `other`  
 Başka bir VectorViewIterator.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`Geçerli VectorViewIterator değerinden büyük veya eşit olup olmadığını `other`; Aksi halde, `false`.  
  


## <a name="operator-increment"></a>VectorViewIterator::operator ++ işleci
Geçerli VectorViewIterator artırır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
  
VectorViewIterator& operator++();  
VectorViewIterator operator++(int);  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk sözdizimi artırır ve geçerli VectorViewIterator döndürür. İkinci sözdizimi geçerli VectorViewIterator kopyasını döndürür ve geçerli VectorViewIterator artırır.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk VectorViewIterator sözdizimi geçerli VectorViewIterator önceden artırır.  
  
 İkinci sözdizimi geçerli VectorViewIterator sonrası artırır. `int` İkinci sözdiziminde türü değil gerçek tamsayı işleneni bir sonrası artırma işlemi gösterir.  
  


## <a name="operator-inequality"></a>VectorViewIterator::operator! = işleci
Geçerli VectorViewIterator için belirtilen VectorViewIterator eşit olup olmadığını gösterir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
bool operator!=(const VectorViewIterator& other) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `other`  
 Başka bir VectorViewIterator.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`Geçerli VectorViewIterator eşit değilse `other`; Aksi halde, `false`.  
  


## <a name="operator-less-than"></a>VectorViewIterator::operator&lt; işleci
Geçerli VectorIterator belirtilen VectorIterator değerinden olup olmadığını gösterir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
bool operator<(const VectorViewIterator& other) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `other`  
 Başka bir VectorIterator.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`Geçerli VectorIterator ise değerinden `other`; Aksi halde, `false`.  
  


## <a name="operator-less-than-or-equals"></a>VectorViewIterator::operator&lt;= işleci
Geçerli VectorIterator küçük veya bu belirtilen VectorIterator eşit olup olmadığını gösterir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
  
bool operator<=(const VectorViewIterator& other) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `other`  
 Başka bir VectorIterator.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`Geçerli VectorIterator küçük veya eşit olup olmadığını `other`; Aksi halde, `false`.  
  


## <a name="operator-minus"></a>VectorViewIterator::operator işleci
Yineleyiciler arasında öğe sayısını verir geçerli yineleyici öğesinden yeni yineleyici ya da belirtilen yineleyici oluşturan geçerli yineleyici öğelerini itibaren belirli sayıda çıkarır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
  
VectorViewIterator operator-(difference_type n) const;  
  
difference_type operator-(const VectorViewIterator& other) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `n`  
 Öğe sayısı.  
  
 `other`  
 Başka bir VectorViewIterator.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk işleci söz dizimi olan bir VectorViewIterator nesnesi döndüren `n` öğeleri geçerli VectorViewIterator küçüktür. İkinci işleci sözdizimi geçerli öğe sayısını döndürür ve `other` VectorViewIterator.  
  


## <a name="operator-plus-equals"></a>VectorViewIterator::operator += işleci
Geçerli VectorViewIterator tarafından belirtilen öteleme artırır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
VectorViewIterator& operator+=(difference_type n);  
```  
  
### <a name="parameters"></a>Parametreler  
 `n`  
 Bir tamsayı öteleme.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Güncelleştirilmiş VectorViewIterator.  
  


## <a name="operator-plus"></a>VectorViewIterator::operator + işleci
Belirtilen öteleme öğede belirtilen VectorViewIterator başvuruda bulunan bir VectorViewIterator döndürür.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
  
VectorViewIterator operator+(difference_type n) const;  
  
template <typename T>   
inline VectorViewIterator<T> operator+  
   (ptrdiff_t n,   
   const VectorViewIterator<T>& i);  
  
```  
  
### <a name="parameters"></a>Parametreler  
 `T`  
 İkinci sözdizimi, VectorViewIterator typename.  
  
 `n`  
 Bir tamsayı öteleme.  
  
 `i`  
 İkinci sözdizimi, bir VectorViewIterator.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk sözdizimi, belirtilen öteleme öğede geçerli VectorViewIterator başvuruda bulunan bir VectorViewIterator.  
  
 Belirtilen öteleme öğede parametre baştan başvuruda bulunan bir VectorViewIterator ikinci sözdiziminde `i`.  
  


## <a name="operator-minus-assign"></a>VectorViewIterator::operator-= işleci
Belirtilen öteleme tarafından geçerli VectorIterator azaltır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
VectorViewIterator& operator-=(difference_type n);  
```  
  
### <a name="parameters"></a>Parametreler  
 `n`  
 Bir tamsayı öteleme.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Güncelleştirilmiş VectorIterator.  
  


## <a name="operator-at"></a>VectorViewIterator::operator\[\]
Belirtilen öteleme geçerli VectorViewIterator gelen olan öğe için bir başvuru alır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
reference operator[](difference_type n) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `n`  
 Bir tamsayı öteleme.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tarafından hatalı yerleştirilen öğeyi `n` geçerli VectorViewIterator öğelerinden.  
  


## <a name="ctor"></a>VectorViewIterator::VectorViewIterator Oluşturucusu
VectorViewIterator sınıfının yeni bir örneğini başlatır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
  
VectorViewIterator();  
  
explicit VectorViewIterator(  
   Windows::Foundation::Collections::IVectorView<T>^ v  
);  
```  
  
### <a name="parameters"></a>Parametreler  
 `v`  
 Bir IVectorView\<T > nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk sözdizimi varsayılan oluşturucu örnektir. Bir IVectorView gelen VectorViewIterator oluşturmak için kullanılan bir açık Oluşturucu ikinci sözdizimi örnektir\<T > nesne.  
  

  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Platform Namespace](platform-namespace-c-cx.md)