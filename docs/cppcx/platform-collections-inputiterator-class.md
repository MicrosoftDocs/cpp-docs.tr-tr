---
title: Platform::Collections::InputIterator sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- COLLECTION/Platform::Collections::InputIterator::InputIterator
dev_langs:
- C++
helpviewer_keywords:
- InputIterator Class
ms.assetid: ef72eea4-32a9-42b9-8119-ce87dbdcd3be
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7188cba0655e2ca89f82b60ffe9ee4b8ce94633a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33089097"
---
# <a name="platformcollectionsinputiterator-class"></a>Platform::Collections::InputIterator sınıfı
Windows çalışma zamanı türetilen koleksiyonlar için bir standart Şablon kitaplığı InputIterator sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <typename X>  
class InputIterator;  
```  
  
#### <a name="parameters"></a>Parametreler  
 `X`  
 InputIterator Şablon sınıfı typename.  
  
### <a name="members"></a>Üyeler  
  
### <a name="public-typedefs"></a>Genel tür tanımları  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`difference_type`|İşaretçi fark (ptrdiff_t).|  
|`iterator_category`|Bir giriş yineleyici kategorisini (:: std::input_iterator_tag).|  
|`pointer`|Bir işaretçi bir `const X`|  
|`reference`|Bir başvuru bir `const X`|  
|`value_type`|`X` Typename.|  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[InputIterator::InputIterator](#ctor)|InputIterator sınıfının yeni bir örneğini başlatır.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[InputIterator::operator! = işleci](#operator-inequality)|Geçerli InputIterator için belirtilen InputIterator eşit olup olmadığını gösterir.|  
|[InputIterator::operator * işleci](#operator-decrement)|Geçerli InputIterator tarafından belirtilen öğenin bir başvuru alır.|  
|[InputIterator::operator ++ işleci](#operator-increment)|Geçerli InputIterator artırır.|  
|[InputIterator::operator == işleci](#operator-equality)|Geçerli InputIterator için belirtilen InputIterator eşit olup olmadığını gösterir.|  
|[InputIterator::operator -> işleci](#operator-arrow)|Geçerli InputIterator tarafından başvurulan öğenin adresi alır.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `InputIterator`  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** collection.h  
  
 **Namespace:** Platform::Collections  

## <a name="ctor"></a>  InputIterator::InputIterator Oluşturucusu
InputIterator sınıfının yeni bir örneğini başlatır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
InputIterator();  
explicit InputIterator(Windows::Foundation::Collections<X>^ iter);  
```  
  
### <a name="parameters"></a>Parametreler  
 `iter`  
 Yineleyici nesne.  
  


## <a name="operator-arrow"></a>  InputIterator::operator -&gt; işleci
Geçerli InputIterator tarafından belirtilen öğenin adresini alır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
pointer operator->() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli InputIterator tarafından belirtilen öğenin adresi.  
  


## <a name="operator-dereference"></a>  InputIterator::operator * işleci
Geçerli InputIterator tarafından belirtilen öğenin bir başvuru alır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
reference operator*() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli InputIterator tarafından belirtilen öğesi.  
  


## <a name="operator-equality"></a>  InputIterator::operator == işleci
Geçerli InputIterator için belirtilen InputIterator eşit olup olmadığını gösterir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
bool operator== (const InputIterator& other) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `other`  
 Başka bir InputIterator.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true` Geçerli InputIterator eşitse `other`; Aksi halde, `false`.  
  


## <a name="operator-increment"></a>  InputIterator::operator ++ işleci
Geçerli InputIterator artırır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```    
InputIterator& operator++();   
InputIterator operator++(int);  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk sözdizimi artırır ve geçerli InputIterator döndürür. İkinci sözdizimi geçerli InputIterator kopyasını döndürür ve geçerli InputIterator artırır.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk InputIterator sözdizimi geçerli InputIterator önceden artırır.  
  
 İkinci sözdizimi geçerli InputIterator sonrası artırır. `int` İkinci sözdiziminde türü değil gerçek tamsayı işleneni bir sonrası artırma işlemi gösterir.  
  


## <a name="operator-inequality"></a>  InputIterator::operator! = işleci
Geçerli InputIterator için belirtilen InputIterator eşit olup olmadığını gösterir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
bool operator!=(const InputIterator& other) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `other`  
 Başka bir InputIterator.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true` Geçerli InputIterator eşit değilse `other`; Aksi halde, `false`.   

  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Platform Namespace](platform-namespace-c-cx.md)