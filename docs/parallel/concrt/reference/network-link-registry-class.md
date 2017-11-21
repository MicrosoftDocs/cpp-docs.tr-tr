---
title: "network_link_registry sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- network_link_registry
- AGENTS/concurrency::network_link_registry
- AGENTS/concurrency::network_link_registry::add
- AGENTS/concurrency::network_link_registry::begin
- AGENTS/concurrency::network_link_registry::contains
- AGENTS/concurrency::network_link_registry::count
- AGENTS/concurrency::network_link_registry::remove
dev_langs: C++
helpviewer_keywords: network_link_registry class
ms.assetid: 3e7b4097-09f1-4252-964e-b15b8f7f7fc6
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 348964eb2f9b17a00188dd3a2589ce0711767e64
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="networklinkregistry-class"></a>network_link_registry Sınıfı
`network_link_registry` Özet temel sınıf kaynak ve hedef blokları arasındaki bağlantıları yönetir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<class _Block>
class network_link_registry;
```  
  
#### <a name="parameters"></a>Parametreler  
 `_Block`  
 Blok veri türü depolanıyor `network_link_registry`.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-typedefs"></a>Genel tür tanımları  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`const_pointer`|Bir işaretçi sağlayan bir türü bir `const` öğesinde bir `network_link_registry` nesnesi.|  
|`const_reference`|Bir başvuru sağlayan bir türü bir `const` öğesi saklanan bir `network_link_registry` nesne için okuma ve const işlemlerini gerçekleştirme.|  
|`iterator`|Yineleyici sağlayan bir tür okuma veya herhangi bir öğe değiştirme bir `network_link_registry` nesnesi.|  
|`type`|Depolanan blok türü temsil eden bir tür `network_link_registry` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[ekleme](#add)|Türetilen bir sınıfta geçersiz kılındığında, bir bağlantı ekler `network_link_registry` nesnesi.|  
|[başlayın](#begin)|Türetilen bir sınıfta geçersiz kılındığında, yineleyici ilk öğe döndürür `network_link_registry` nesnesi.|  
|[içerir](#contains)|Türetilen bir sınıfta geçersiz kılındığında, arar `network_link_registry` belirtilen bloğu için nesnesi.|  
|[sayısı](#count)|Türetilen bir sınıfta geçersiz kılındığında, öğelerin sayısını döndürür `network_link_registry` nesnesi.|  
|[Kaldır](#remove)|Türetilen bir sınıfta geçersiz kılındığında, belirtilen bloğundan kaldırır `network_link_registry` nesnesi.|  
  
## <a name="remarks"></a>Açıklamalar  
 `network link registry` Eş zamanlı erişim için güvenli değildir.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `network_link_registry`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** agents.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="add"></a>ekleme 

 Türetilen bir sınıfta geçersiz kılındığında, bir bağlantı ekler `network_link_registry` nesnesi.  
  
```
virtual void add(_EType _Link) = 0;
```  
  
### <a name="parameters"></a>Parametreler  
 `_Link`  
 Eklenecek bir bloğu için bir işaretçi.  
  
##  <a name="begin"></a>başlayın 

 Türetilen bir sınıfta geçersiz kılındığında, yineleyici ilk öğe döndürür `network_link_registry` nesnesi.  
  
```
virtual iterator begin() = 0;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk öğe adresleme yineleyici `network_link_registry` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Yineleyici son durumu tarafından belirtilen bir `NULL` bağlantı.  
  
##  <a name="contains"></a>içerir 

 Türetilen bir sınıfta geçersiz kılındığında, arar `network_link_registry` belirtilen bloğu için nesnesi.  
  
```
virtual bool contains(_EType _Link) = 0;
```  
  
### <a name="parameters"></a>Parametreler  
 `_Link`  
 İçin de Aranmakta olan bloğu için bir işaretçi `network_link_registry` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`Blok bulunduysa `false` Aksi takdirde.  
  
##  <a name="count"></a>sayısı 

 Türetilen bir sınıfta geçersiz kılındığında, öğelerin sayısını döndürür `network_link_registry` nesnesi.  
  
```
virtual size_t count() = 0;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğelerin sayısı `network_link_registry` nesnesi.  
  
##  <a name="remove"></a>Kaldır 

 Türetilen bir sınıfta geçersiz kılındığında, belirtilen bloğundan kaldırır `network_link_registry` nesnesi.  
  
```
virtual bool remove(_EType _Link) = 0;
```  
  
### <a name="parameters"></a>Parametreler  
 `_Link`  
 Bir blok, kaldırılması için bir işaretçi bulundu.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`bağlantı bulundu ve kaldırıldı, `false` Aksi takdirde.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Namespace](concurrency-namespace.md)   
 [single_link_registry sınıfı](single-link-registry-class.md)   
 [multi_link_registry sınıfı](multi-link-registry-class.md)
