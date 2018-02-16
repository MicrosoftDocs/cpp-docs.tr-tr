---
title: "Platform::Collections::BackInsertIterator sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COLLECTION/Platform::Collections::BackInsertIterator::BackInsertIterator
dev_langs:
- C++
helpviewer_keywords:
- BackInsertIterator Class
ms.assetid: aecee1ff-100d-4129-b84b-1966f0923dbf
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 23c8b657a6cafb720cf0be07e2e67b5af0d7767d
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="platformcollectionsbackinsertiterator-class"></a>Platform::Collections::BackInsertIterator sınıfı
Geçersiz kılar, sıralı bir koleksiyonu arka ucunu elemanlara yerine ekler yineleyici temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <typename T>  
class BackInsertIterator : 
public ::std::iterator<::std::output_iterator_tag, void, void, void, void>;  
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Geçerli koleksiyondaki öğe türü.  
  
### <a name="remarks"></a>Açıklamalar  
 BackInsertIterator sınıfı tarafından gereken kuralları uygular [back_insert_iterator sınıfı](../standard-library/back-insert-iterator-class.md).  
  
### <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[BackInsertIterator::BackInsertIterator](#ctor)|BackInsertIterator sınıfının yeni bir örneğini başlatır.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[BackInsertIterator::operator* Operator](#operator-dereference)|Geçerli BackInsertIterator bir başvuru alır.|  
|[BackInsertIterator::operator++ Operator](#operator-increment)|Geçerli BackInsertIterator bir başvuru döndürür. Yineleyici değiştirilmez.|  
|[BackInsertIterator::operator= Operator](#operator-assign)|Belirtilen nesne geçerli sıralı koleksiyonun sonuna ekler.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `BackInsertIterator`  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** collection.h  
  
 **Namespace:** Platform::Collections  
  
---
## <a name="ctor"></a>  BackInsertIterator::BackInsertIterator Oluşturucusu
Yeni bir örneğini başlatır `BackInsertIterator` sınıfı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
explicit BackInsertIterator(  
   Windows::Foundation::Collections::IVector<T>^ v);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `v`  
 Bir IVector\<T > nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 A `BackInsertIterator` parametresi tarafından belirtilen nesnesinin son öğesinden sonra öğeleri ekler `v`.  
 
## <a name="operator-assign"></a>  BackInsertIterator::operator= Operator
Belirtilen nesne geçerli sıralı koleksiyonun sonuna ekler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```    
BackInsertIterator& operator=( const T& t);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `t`  
 Geçerli koleksiyona eklenecek nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli BackInsertIterator referansı.  

## <a name="operator-dereference"></a>  BackInsertIterator::operator * işleci
Geçerli BackInsertIterator bir başvuru alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
BackInsertIterator& operator*();  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli BackInsertIterator referansı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işleç geçerli BackInsertIterator bir başvuru döndürür; olmayan herhangi bir öğeye geçerli koleksiyonunda.  
 
## <a name="operator-increment"></a>  BackInsertIterator::operator++ Operator
Geçerli BackInsertIterator bir başvuru döndürür. Yineleyici değiştirilmez.  
  
## <a name="syntax"></a>Sözdizimi  
  
``` 
  
BackInsertIterator& operator++();  
  
BackInsertIterator operator++(int);  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli BackInsertIterator referansı.  
  
### <a name="remarks"></a>Açıklamalar  
 Tasarıma göre ilk sözdizimi örneği geçerli BackInsertIterator önceden artırır ve ikinci sözdizimi geçerli BackInsertIterator sonrası artırır. `int` İkinci sözdiziminde türü değil gerçek tamsayı işleneni bir sonrası artırma işlemi gösterir.  
  
 Ancak, bu işleç BackInsertIterator gerçekten değiştirmez. Bunun yerine, bu işleç değiştirilmemiş, geçerli yineleyici bir başvuru döndürür. Aynı davranışı budur [işleç *](#dereference-operator).  
  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Platform Namespace](platform-namespace-c-cx.md)