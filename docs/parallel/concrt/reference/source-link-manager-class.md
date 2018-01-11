---
title: "source_link_manager sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- source_link_manager
- AGENTS/concurrency::source_link_manager
- AGENTS/concurrency::source_link_manager::source_link_manager
- AGENTS/concurrency::source_link_manager::add
- AGENTS/concurrency::source_link_manager::begin
- AGENTS/concurrency::source_link_manager::contains
- AGENTS/concurrency::source_link_manager::count
- AGENTS/concurrency::source_link_manager::reference
- AGENTS/concurrency::source_link_manager::register_target_block
- AGENTS/concurrency::source_link_manager::release
- AGENTS/concurrency::source_link_manager::remove
- AGENTS/concurrency::source_link_manager::set_bound
dev_langs: C++
helpviewer_keywords: source_link_manager class
ms.assetid: 287487cf-e0fe-4c35-aa3c-24f081d1ddae
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 67cf15c6681c989a2da2b4e6824fec6012c517bf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="sourcelinkmanager-class"></a>source_link_manager Sınıfı
`source_link_manager` Nesnesi ileti bloğu ağ bağlantıları yönetir `ISource` engeller.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<class _LinkRegistry>
class source_link_manager;
```  
  
#### <a name="parameters"></a>Parametreler  
 `_LinkRegistry`  
 Ağ bağlantısı kayıt.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-typedefs"></a>Genel tür tanımları  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`const_pointer`|Bir işaretçi sağlayan bir türü bir `const` öğesinde bir `source_link_manager` nesnesi.|  
|`const_reference`|Bir başvuru sağlayan bir türü bir `const` öğesi saklanan bir `source_link_manager` nesne için okuma ve const işlemlerini gerçekleştirme.|  
|`iterator`|Yineleyici sağlayan bir tür okuma veya herhangi bir öğe değiştirme `source_link_manager` nesnesi.|  
|`type`|Bağlantı kayıt defteri tarafından yönetilen türü `source_link_manager` nesnesi.|  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[source_link_manager](#ctor)|Oluşturan bir `source_link_manager` nesnesi.|  
|[~ source_link_manager yok Edicisi](#dtor)|Bozar `source_link_manager` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[add](#add)|Kaynak bağlantısı ekler `source_link_manager` nesnesi.|  
|[başlayın](#begin)|Yineleyici ilk öğe döndürür `source_link_manager` nesnesi.|  
|[içerir](#contains)|Aramaları `network_link_registry` bu içinde `source_link_manager` belirtilen bloğu için nesnesi.|  
|[sayısı](#count)|Bağlantılı bloklarında sayar `source_link_manager` nesnesi.|  
|[başvuru](#reference)|Üzerinde bir başvuru edinir `source_link_manager` nesnesi.|  
|[register_target_block](#register_target_block)|Bu tutan hedef blok kaydeder `source_link_manager` nesnesi.|  
|[Sürüm](#release)|Üzerinde başvuru serbest `source_link_manager` nesnesi.|  
|[remove](#remove)|Bir bağlantıdan kaldırır `source_link_manager` nesnesi.|  
|[set_bound](#set_bound)|Bu eklenebilir kaynak bağlantı sayısının üst sınırını ayarlar `source_link_manager` nesnesi.|  
  
## <a name="remarks"></a>Açıklamalar  
 Şu anda kaynak sayılan başvuru taşlarıdır. Bu sarmalayıcı olan bir `network_link_registry` bağlantıları eş zamanlı erişim sağlar ve bağlantılar geri çağırmalar aracılığıyla başvuru olanağı sağlayan nesne. İleti blokları ( `target_block`s veya `propagator_block`s) Bu sınıf için kendi kaynak bağlantıları kullanmanız gerekir.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `source_link_manager`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** agents.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="add"></a>ekleme 

 Kaynak bağlantısı ekler `source_link_manager` nesnesi.  
  
```
void add(_EType _Link);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Link`  
 Eklenecek bir bloğu için bir işaretçi.  
  
##  <a name="begin"></a>başlayın 

 Yineleyici ilk öğe döndürür `source_link_manager` nesnesi.  
  
```
iterator begin();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk öğe adresleme yineleyici `source_link_manager` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Yineleyici son durumu tarafından belirtilen bir `NULL` bağlantı.  
  
##  <a name="contains"></a>içerir 

 Aramaları `network_link_registry` bu içinde `source_link_manager` belirtilen bloğu için nesnesi.  
  
```
bool contains(_EType _Link);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Link`  
 İçinde aranacak bir bloğu için bir işaretçi `source_link_manager` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`Belirtilen blok bulunduysa `false` Aksi takdirde.  
  
##  <a name="count"></a>sayısı 

 Bağlantılı bloklarında sayar `source_link_manager` nesnesi.  
  
```
size_t count();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bağlantılı blok sayısını `source_link_manager` nesnesi.  
  
##  <a name="reference"></a>başvuru 

 Üzerinde bir başvuru edinir `source_link_manager` nesnesi.  
  
```
void reference();
```  
  
##  <a name="register_target_block"></a>register_target_block 

 Bu tutan hedef blok kaydeder `source_link_manager` nesnesi.  
  
```
void register_target_block(_Inout_ ITarget<typename _Block::source_type>* _PTarget);
```  
  
### <a name="parameters"></a>Parametreler  
 `_PTarget`  
 Bu bulunduran hedef blok `source_link_manager` nesnesi.  
  
##  <a name="release"></a>Sürüm 

 Üzerinde başvuru serbest `source_link_manager` nesnesi.  
  
```
void release();
```  
  
##  <a name="remove"></a>Kaldır 

 Bir bağlantıdan kaldırır `source_link_manager` nesnesi.  
  
```
bool remove(_EType _Link);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Link`  
 Bir blok, kaldırılması için bir işaretçi bulundu.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`bağlantı bulundu ve kaldırıldı, `false` Aksi takdirde.  
  
##  <a name="set_bound"></a>set_bound 

 Bu eklenebilir kaynak bağlantı sayısının üst sınırını ayarlar `source_link_manager` nesnesi.  
  
```
void set_bound(size_t _MaxLinks);
```  
  
### <a name="parameters"></a>Parametreler  
 `_MaxLinks`  
 Bağlantılarının maksimum sayısı.  
  
##  <a name="ctor"></a>source_link_manager 

 Oluşturan bir `source_link_manager` nesnesi.  
  
```
source_link_manager();
```  
  
##  <a name="dtor"></a>~ source_link_manager 

 Bozar `source_link_manager` nesnesi.  
  
```
~source_link_manager();
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Namespace](concurrency-namespace.md)   
 [single_link_registry sınıfı](single-link-registry-class.md)   
 [multi_link_registry Sınıfı](multi-link-registry-class.md)
