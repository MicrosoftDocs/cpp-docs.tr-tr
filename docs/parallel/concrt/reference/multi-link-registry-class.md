---
title: "multi_link_registry sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- multi_link_registry
- AGENTS/concurrency::multi_link_registry
- AGENTS/concurrency::multi_link_registry::multi_link_registry
- AGENTS/concurrency::multi_link_registry::add
- AGENTS/concurrency::multi_link_registry::begin
- AGENTS/concurrency::multi_link_registry::contains
- AGENTS/concurrency::multi_link_registry::count
- AGENTS/concurrency::multi_link_registry::remove
- AGENTS/concurrency::multi_link_registry::set_bound
dev_langs: C++
helpviewer_keywords: multi_link_registry class
ms.assetid: b2aa73a8-e8a6-4255-b117-d07530c328b2
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c5d95a98d56ea666ed823f3caef2190dea1591cb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="multilinkregistry-class"></a>multi_link_registry Sınıfı
`multi_link_registry` Nesne bir `network_link_registry` birden çok kaynak blokları veya birden çok hedef blokları yönetir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<class _Block>
class multi_link_registry : public network_link_registry<_Block>;
```  
  
#### <a name="parameters"></a>Parametreler  
 `_Block`  
 Blok veri türü depolanıyor `multi_link_registry` nesnesi.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[multi_link_registry](#ctor)|Oluşturan bir `multi_link_registry` nesnesi.|  
|[~ multi_link_registry yok Edicisi](#dtor)|Bozar `multi_link_registry` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[add](#add)|Bir bağlantı ekler `multi_link_registry` nesnesi. (Geçersiz kılmaları [network_link_registry::add](network-link-registry-class.md#add).)|  
|[başlayın](#begin)|Yineleyici ilk öğe döndürür `multi_link_registry` nesnesi. (Geçersiz kılmaları [network_link_registry::begin](network-link-registry-class.md#begin).)|  
|[içerir](#contains)|Aramaları `multi_link_registry` belirtilen bloğu için nesnesi. (Geçersiz kılmaları [network_link_registry::contains](network-link-registry-class.md#contains).)|  
|[sayısı](#count)|Öğeleri sayar `multi_link_registry` nesnesi. (Geçersiz kılmaları [network_link_registry::count](network-link-registry-class.md#count).)|  
|[remove](#remove)|Bir bağlantıdan kaldırır `multi_link_registry` nesnesi. (Geçersiz kılmaları [network_link_registry::remove](network-link-registry-class.md#remove).)|  
|[set_bound](#set_bound)|Bağlantı sayısı üst sınırı ayarlayan `multi_link_registry` hold nesnesi.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [network_link_registry](network-link-registry-class.md)  
  
 `multi_link_registry`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** agents.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="add"></a>ekleme 

 Bir bağlantı ekler `multi_link_registry` nesnesi.  
  
```
virtual void add(_EType _Link);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Link`  
 Eklenecek bir bloğu için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Yöntem oluşturulur bir [invalid_link_target](invalid-link-target-class.md) özel durum bağlantıyı kayıt defterinde zaten varsa veya bir bağlama zaten ayarlanmış ile `set_bound` işlevi ve bağlantı kaldırılmışsa.  
  
##  <a name="begin"></a>başlayın 

 Yineleyici ilk öğe döndürür `multi_link_registry` nesnesi.  
  
```
virtual iterator begin();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk öğe adresleme yineleyici `multi_link_registry` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Son durum belirtilir bir `NULL` bağlantı.  
  
##  <a name="contains"></a>içerir 

 Aramaları `multi_link_registry` belirtilen bloğu için nesnesi.  
  
```
virtual bool contains(_EType _Link);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Link`  
 İçinde aranacak bir bloğu için bir işaretçi `multi_link_registry` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`Belirtilen blok bulunduysa `false` Aksi takdirde.  
  
##  <a name="count"></a>sayısı 

 Öğeleri sayar `multi_link_registry` nesnesi.  
  
```
virtual size_t count();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğelerin sayısı `multi_link_registry` nesnesi.  
  
##  <a name="ctor"></a>multi_link_registry 

 Oluşturan bir `multi_link_registry` nesnesi.  
  
```
multi_link_registry();
```  
  
##  <a name="dtor"></a>~ multi_link_registry 

 Bozar `multi_link_registry` nesnesi.  
  
```
virtual ~multi_link_registry();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Yöntem oluşturulur bir [invalid_operation](invalid-operation-class.md) tüm bağlantılar kaldırılır önce çağırılır, özel durum.  
  
##  <a name="remove"></a>Kaldır 

 Bir bağlantıdan kaldırır `multi_link_registry` nesnesi.  
  
```
virtual bool remove(_EType _Link);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Link`  
 Bir blok, kaldırılması için bir işaretçi bulundu.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`bağlantı bulundu ve kaldırıldı, `false` Aksi takdirde.  
  
##  <a name="set_bound"></a>set_bound 

 Bağlantı sayısı üst sınırı ayarlayan `multi_link_registry` hold nesnesi.  
  
```
void set_bound(size_t _MaxLinks);
```  
  
### <a name="parameters"></a>Parametreler  
 `_MaxLinks`  
 En fazla bağlantı `multi_link_registry` hold nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bağımlı ayarlandıktan sonra bir giriş kaynağınızın neden olur `multi_link_registry` değişmez durumuna girmesini nesnesine burada çağrıları daha fazla `add` özel durum oluşturacak bir `invalid_link_target` özel durum.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Namespace](concurrency-namespace.md)   
 [single_link_registry Sınıfı](single-link-registry-class.md)
