---
title: CONCURRENCY::Direct3D Namespace | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amp/Concurrency::direct3d
- amprt/Concurrency::direct3d
- amp_short_vectors/Concurrency::direct3d
- amp_graphics/Concurrency::direct3d
- amp_math/Concurrency::direct3d
dev_langs: C++
helpviewer_keywords: direct3d namespace
ms.assetid: 9566a2f1-4d5f-43e4-a3ac-676643d38420
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 849f430caaaf8dacef53ecedd5dc4897041b624a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="concurrencydirect3d-namespace"></a>Concurrency::direct3d Ad Alanı
`direct3d` Ad alanı, D3D birlikte çalışabilirlik desteği işlevleri sağlar. Bu işlem AMP kodda D3D kaynaklarının sorunsuz kullanımını sağlar yanı sıra Ara yedek kopya oluşturmak zorunda kalmadan D3D kodda AMP içinde oluşturulan kaynakları kullanılmasına izin verin. Artımlı olarak C++ AMP kullanarak DirectX uygulamalarınızı işlem yoğunluklu bölümlerini hızlandırmak ve AMP hesaplamalar üretilen veriler üzerinde D3D API kullanın.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
namespace direct3d;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="classes"></a>Sınıflar  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[scoped_d3d_access_lock sınıfı](scoped-d3d-access-lock-class.md)|RAII sarmalayıcı D3D erişim kilit için bir `accelerator_view` nesnesi.|  
  
### <a name="structures"></a>Yapılar  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[adopt_d3d_access_lock_t yapısı](adopt-d3d-access-lock-t-structure.md)|D3D erişim kilit göstermek için etiket türünü benimsenen edinilen yerine.|  
  
### <a name="functions"></a>İşlevler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Abs](concurrency-direct3d-namespace-functions-amp.md#abs)|Bağımsız değişken mutlak değerini döndürür|  
|[CLAMP](concurrency-direct3d-namespace-functions-amp.md#clamp)|Fazla Yüklendi. Belirtilen _Min ve _en aralığına _X clamps|  
|[countbits](concurrency-direct3d-namespace-functions-amp.md#countbits)|_X kümesi bit sayısını sayar|  
|[create_accelerator_view](concurrency-direct3d-namespace-functions-amp.md#create_accelerator_view)|Oluşturur bir [accelerator_view sınıfı](accelerator-view-class.md) Direct3D aygıt arabirimi için bir işaretçi gelen|  
|[d3d_access_lock](concurrency-direct3d-namespace-functions-amp.md#d3d_access_lock)|Güvenli bir şekilde D3D işlemleri ile accelerator_view paylaşılan kaynaklar amacıyla bir accelerator_view üzerinde bir kilit alır|  
|[d3d_access_try_lock](concurrency-direct3d-namespace-functions-amp.md#d3d_access_try_lock)|D3D erişim bir accelerator_view engellenmeden Kilitle girişimi.|  
|[d3d_access_unlock](concurrency-direct3d-namespace-functions-amp.md#d3d_access_unlock)|Verilen accelerator_view D3D erişim kilidi serbest bırakın.|  
|[firstbithigh](concurrency-direct3d-namespace-functions-amp.md#firstbithigh)|En yüksek sıra bit başlatma ve aşağı çalışma _X ilk kümesi bit konumunu alır|  
|[firstbitlow](concurrency-direct3d-namespace-functions-amp.md#firstbitlow)|En düşük sıra bit başlatma ve yukarı çalışma _X ilk kümesi bit konumunu alır|  
|[get_buffer](concurrency-direct3d-namespace-functions-amp.md#get_buffer)|Bir dizi temel D3D arabellek arabirimi alın.|  
|[imax](concurrency-direct3d-namespace-functions-amp.md#imax)|Büyük değer döndürme iki değerlerini karşılaştırır.|  
|[imin](concurrency-direct3d-namespace-functions-amp.md#imin)|Daha küçük olan değer döndürme iki değerlerini karşılaştırır.|  
|[is_timeout_disabled](concurrency-direct3d-namespace-functions-amp.md#is_timeout_disabled)|Zaman aşımı için belirtilen accelerator_view devre dışı olup olmadığını gösteren bir Boole bayrağı döndürür.|  
|[MAD](concurrency-direct3d-namespace-functions-amp.md#mad)|Fazla Yüklendi. Üç bağımsız değişkenler aritmetik Çarp/ekleme işlemi gerçekleştirir: _X * _Y + _Z|  
|[make_array](concurrency-direct3d-namespace-functions-amp.md#make_array)|Bir dizi D3D arabellek arabirimi işaretçi oluşturun.|  
|[gürültü](concurrency-direct3d-namespace-functions-amp.md#noise)|Rastgele bir değeri Perlin gürültü algoritması kullanılarak oluşturur|  
|[radyan cinsinden](concurrency-direct3d-namespace-functions-amp.md#radians)|_X derece radyan için dönüştürür.|  
|[rcp](concurrency-direct3d-namespace-functions-amp.md#rcp)|Hızlı, yaklaşık devrik bağımsız değişkenin hesaplar|  
|[reversebits](concurrency-direct3d-namespace-functions-amp.md#reversebits)|_X bitleri sırasını tersine çevirir|  
|[saturate](concurrency-direct3d-namespace-functions-amp.md#saturate)|0 ve 1 aralığında _X clamps|  
|[oturum](concurrency-direct3d-namespace-functions-amp.md#sign)|Fazla Yüklendi. Bağımsız değişken işaretini döndürür|  
|[smoothstep](concurrency-direct3d-namespace-functions-amp.md#smoothstep)|_X [_Min, _en] aralığında bir kesintisiz Hermite ilişkilendirme 0 ile 1 arasında döndürür.|  
|[Adım](concurrency-direct3d-namespace-functions-amp.md#step)|İki değer, 0 veya 1 hangi değerin büyük olduğuna bağlı olarak döndüren karşılaştırır|  
|[UMAX](concurrency-direct3d-namespace-functions-amp.md#umax)|Büyük değer döndürme iki imzasız değerlerini karşılaştırır.|  
|[umin](concurrency-direct3d-namespace-functions-amp.md#umin)|Daha küçük olan değer döndürme iki imzasız değerlerini karşılaştırır.|  

## <a name="requirements"></a>Gereksinimler  
 **Başlık:** amp.h  
  
 **Namespace:** eşzamanlılık  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Namespace (C++ AMP)](concurrency-namespace-cpp-amp.md)
