---
title: Platform::ArrayReference sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::ArrayReference::ArrayReference
dev_langs:
- C++
helpviewer_keywords:
- Platform::ArrayReference Class
ms.assetid: 9ab3b15e-8a60-4600-8fcb-7d6c86284f4b
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c8e4183c400cf45a23f24a98292b68f6df537da1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33089120"
---
# <a name="platformarrayreference-class"></a>Platform::ArrayReference sınıfı
`ArrayReference` için alternatif bir en iyi duruma getirme türü [Platform::Array ^](../cppcx/platform-array-class.md) C stili dizi giriş verilerle doldurmak istediğiniz zaman giriş parametrelerinde.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
class ArrayReference  
```
  
### <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[ArrayReference::ArrayReference](#ctor)|Yeni bir örneğini başlatır `ArrayReference` sınıfı.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[ArrayReference::operator() işleci](#operator-call)|Bu dönüştürür `ArrayReference` için bir `Platform::Array<T>^*`.|  
|[ArrayReference::operator = işleci](#operator-assign)|İçeriği başka bir atar `ArrayReference` Bu örnek için.|  
  
## <a name="exceptions"></a>Özel Durumlar  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanarak `ArrayReference` C stili dizi doldurmak için ilk kopyalama söz konusu ek kopyalama işlemi kaçının bir `Platform::Array` değişken ve ardından halinde C tarzı dizi. Kullandığınızda `ArrayReference`, yalnızca bir kopyalama işlemi yoktur. Kod örneği için bkz: [dizi ve WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md).  
  
### <a name="requirements"></a>Gereksinimler  
 **Desteklenen en düşük istemci:** Windows 8  
  
 **Desteklenen en düşük sunucu:** Windows Server 2012  
  
 **Namespace:** Platform  
  
 **Başlık:** vccorlib.h  
  
## <a name="ctor"></a>  ArrayReference::ArrayReference Oluşturucusu
Yeni bir örneğini başlatır [Platform::ArrayReference](../cppcx/platform-arrayreference-class.md) sınıfı.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
ArrayReference(TArg* ataArg, unsigned int sizeArg, bool needsInitArg = false);  
ArrayReference(ArrayReference&& otherArg)  
  
```  
  
### <a name="parameters"></a>Parametreler  
 `dataArg`  
 Dizi veri için bir işaretçi.  
  
 `sizeArg`  
 Kaynak dizideki öğelerin sayısı.  
  
 `otherArg`  
 Bir `ArrayReference` verisini taşınacak yeni örneği başlatmak nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
  


## <a name="operator-assign"></a>  ArrayReference::operator = işleci
Belirtilen nesne geçerli atar [Platform::ArrayReference](../cppcx/platform-arrayreference-class.md) taşıma semantiği kullanarak nesne.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
  
ArrayReference& operator=(ArrayReference&& otherArg);  
  
```  
  
### <a name="parameters"></a>Parametreler  
 `otherArg`  
 Geçerli taşınır nesne `ArrayReference` nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir başvuru türünde bir nesne `ArrayReference`.  
  
### <a name="remarks"></a>Açıklamalar  
 `Platform::ArrayReference` bir standart C++ sınıfı, ref sınıfı şablonudur.  
  


## <a name="operator-call"></a>  ArrayReference::operator() işleci
Geçerli dönüştürür [Platform::ArrayReference](../cppcx/platform-arrayreference-class.md) geri nesnesini bir [Platform::Array](../cppcx/platform-array-class.md) sınıfı.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
  
Array<TArg>^ operator ();  
  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir tanıtıcı için-nesne türü `Array<TArg>^`  
  
### <a name="remarks"></a>Açıklamalar  
 [Platform::ArrayReference](../cppcx/platform-arrayreference-class.md) ve [Platform::Array](../cppcx/platform-array-class.md) standart C++ sınıf şablonları, değil ref sınıflarıdır.  
  


  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Platform ad alanı](../cppcx/platform-namespace-c-cx.md)