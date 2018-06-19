---
title: single_link_registry sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- single_link_registry
- AGENTS/concurrency::single_link_registry
- AGENTS/concurrency::single_link_registry::single_link_registry
- AGENTS/concurrency::single_link_registry::add
- AGENTS/concurrency::single_link_registry::begin
- AGENTS/concurrency::single_link_registry::contains
- AGENTS/concurrency::single_link_registry::count
- AGENTS/concurrency::single_link_registry::remove
dev_langs:
- C++
helpviewer_keywords:
- single_link_registry class
ms.assetid: 09540a4e-c34e-4ff9-af49-21b8612b6ab3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3220156d201a4dcb7edb6281298d3f248f38fc83
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33690032"
---
# <a name="singlelinkregistry-class"></a>single_link_registry Sınıfı
`single_link_registry` Nesne bir `network_link_registry` yalnızca tek bir kaynak veya hedef blok yönetir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<class _Block>
class single_link_registry : public network_link_registry<_Block>;
```  
  
#### <a name="parameters"></a>Parametreler  
 `_Block`  
 Blok veri türü depolanıyor `single_link_registry` nesnesi.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[single_link_registry](#ctor)|Oluşturan bir `single_link_registry` nesnesi.|  
|[~ single_link_registry yok Edicisi](#dtor)|Bozar `single_link_registry` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[add](#add)|Bir bağlantı ekler `single_link_registry` nesnesi. (Geçersiz kılmaları [network_link_registry::add](network-link-registry-class.md#add).)|  
|[Başlangıç](#begin)|Yineleyici ilk öğe döndürür `single_link_registry` nesnesi. (Geçersiz kılmaları [network_link_registry::begin](network-link-registry-class.md#begin).)|  
|[içerir](#contains)|Aramaları `single_link_registry` belirtilen bloğu için nesnesi. (Geçersiz kılmaları [network_link_registry::contains](network-link-registry-class.md#contains).)|  
|[Sayısı](#count)|Öğeleri sayar `single_link_registry` nesnesi. (Geçersiz kılmaları [network_link_registry::count](network-link-registry-class.md#count).)|  
|[remove](#remove)|Bir bağlantıdan kaldırır `single_link_registry` nesnesi. (Geçersiz kılmaları [network_link_registry::remove](network-link-registry-class.md#remove).)|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [network_link_registry](network-link-registry-class.md)  
  
 `single_link_registry`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** agents.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="add"></a> Ekleme 

 Bir bağlantı ekler `single_link_registry` nesnesi.  
  
```
virtual void add(_EType _Link);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Link`  
 Eklenecek bir bloğu için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Yöntem oluşturulur bir [invalid_link_target](invalid-link-target-class.md) zaten varsa bir bağlantıyı bu kayıt defterinde özel durum.  
  
##  <a name="begin"></a> Başlangıç 

 Yineleyici ilk öğe döndürür `single_link_registry` nesnesi.  
  
```
virtual iterator begin();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk öğe adresleme yineleyici `single_link_registry` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Son durum belirtilir bir `NULL` bağlantı.  
  
##  <a name="contains"></a> içerir 

 Aramaları `single_link_registry` belirtilen bloğu için nesnesi.  
  
```
virtual bool contains(_EType _Link);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Link`  
 İçinde aranacak bir bloğu için bir işaretçi `single_link_registry` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true` bağlantıyı bulunduysa `false` Aksi takdirde.  
  
##  <a name="count"></a> Sayısı 

 Öğeleri sayar `single_link_registry` nesnesi.  
  
```
virtual size_t count();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğelerin sayısı `single_link_registry` nesnesi.  
  
##  <a name="remove"></a> Kaldır 

 Bir bağlantıdan kaldırır `single_link_registry` nesnesi.  
  
```
virtual bool remove(_EType _Link);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Link`  
 Bir blok, kaldırılması için bir işaretçi bulundu.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true` bağlantı bulundu ve kaldırıldı, `false` Aksi takdirde.  
  
##  <a name="ctor"></a> single_link_registry 

 Oluşturan bir `single_link_registry` nesnesi.  
  
```
single_link_registry();
```  
  
##  <a name="dtor"></a> ~ single_link_registry 

 Bozar `single_link_registry` nesnesi.  
  
```
virtual ~single_link_registry();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Yöntem oluşturulur bir [invalid_operation](invalid-operation-class.md) çağrılırsa bağlantıyı kaldırılmadan önce özel durum.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Namespace](concurrency-namespace.md)   
 [multi_link_registry Sınıfı](multi-link-registry-class.md)
