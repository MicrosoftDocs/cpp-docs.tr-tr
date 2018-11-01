---
title: Concurrency::direct3d Ad Alanı
ms.date: 11/04/2016
f1_keywords:
- amp/Concurrency::direct3d
- amprt/Concurrency::direct3d
- amp_short_vectors/Concurrency::direct3d
- amp_graphics/Concurrency::direct3d
- amp_math/Concurrency::direct3d
helpviewer_keywords:
- direct3d namespace
ms.assetid: 9566a2f1-4d5f-43e4-a3ac-676643d38420
ms.openlocfilehash: c99aba319df6f84dbda7b9cf90a1abebdc3757f0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50570358"
---
# <a name="concurrencydirect3d-namespace"></a>Concurrency::direct3d Ad Alanı

`direct3d` Ad alanı D3D birlikte çalışabilirlik destekleyen işlevleri sağlar. AMP kodunda hesaplamak için D3D kaynakların sorunsuz kullanılmasına olanak tanır hem de gereksiz Ara kopyalar oluşturmadan, AMP D3D kodunda oluşturulan kaynakları kullanılmasına izin verin. Artımlı olarak, C++ AMP kullanarak DirectX uygulamalarınızın hesaplama yoğunluklu bölümlerini hızlandırmak ve AMP hesaplamalarıyla üretilen verilerde D3D API'sini kullanın.

## <a name="syntax"></a>Sözdizimi

```
namespace direct3d;
```

## <a name="members"></a>Üyeler

### <a name="classes"></a>Sınıflar

|Ad|Açıklama|
|----------|-----------------|
|[scoped_d3d_access_lock Sınıfı](scoped-d3d-access-lock-class.md)|Bir D3D erişim kilidi için RAII sarmalayıcı bir `accelerator_view` nesne.|

### <a name="structures"></a>Yapılar

|Ad|Açıklama|
|----------|-----------------|
|[adopt_d3d_access_lock_t Yapısı](adopt-d3d-access-lock-t-structure.md)|D3D erişim kilidi belirtmek için etiket türü yerine benimsenmesi.|

### <a name="functions"></a>İşlevler

|Ad|Açıklama|
|----------|-----------------|
|[Abs](concurrency-direct3d-namespace-functions-amp.md#abs)|Bağımsız değişkenin mutlak değerini döndürür|
|[CLAMP](concurrency-direct3d-namespace-functions-amp.md#clamp)|Fazla Yüklendi. Belirtilen _Min ve _Max aralığına _x'i sıkıştırır.|
|[countbits](concurrency-direct3d-namespace-functions-amp.md#countbits)|_X içindeki belirlenmiş bitleri sayar|
|[create_accelerator_view](concurrency-direct3d-namespace-functions-amp.md#create_accelerator_view)|Oluşturur bir [accelerator_view sınıfı](accelerator-view-class.md) bir işaretçiden Direct3D cihaz arayüzü|
|[d3d_access_lock](concurrency-direct3d-namespace-functions-amp.md#d3d_access_lock)|Güvenli şekilde D3D Hızlandırıcı görünümü ile paylaşılan kaynaklarda işlemleri gerçekleştirmek amacıyla bir Hızlandırıcı görünümünde kilit alır|
|[d3d_access_try_lock](concurrency-direct3d-namespace-functions-amp.md#d3d_access_try_lock)|Engelleme olmadan accelerator_view üzerinde D3D erişim kilidi edinmeye çalışın.|
|[d3d_access_unlock](concurrency-direct3d-namespace-functions-amp.md#d3d_access_unlock)|Verilen accelerator_view üzerindeki D3D erişim kilidini serbest bırakın.|
|[firstbithigh](concurrency-direct3d-namespace-functions-amp.md#firstbithigh)|En yüksek sıra bitinden başlayıp ve aşağı doğru çalışma _X içinde ilk belirlenen bitin konumunu alır.|
|[firstbitlow](concurrency-direct3d-namespace-functions-amp.md#firstbitlow)|En düşük sıra bitinden başlayıp ve yukarıya doğru _X içinde ilk belirlenen bitin konumunu alır.|
|[get_buffer](concurrency-direct3d-namespace-functions-amp.md#get_buffer)|Bir dizinin altındaki D3D arabellek arayüzünü alın.|
|[imax](concurrency-direct3d-namespace-functions-amp.md#imax)|Büyük bir değer döndüren iki değeri karşılaştırır.|
|[imin](concurrency-direct3d-namespace-functions-amp.md#imin)|Daha küçük olan bir değer döndüren iki değeri karşılaştırır.|
|[is_timeout_disabled](concurrency-direct3d-namespace-functions-amp.md#is_timeout_disabled)|Zaman aşımı için belirtilen Hızlandırıcı görünümü devre dışı olup olmadığını belirten bir Boole bayrağı döndürür.|
|[mad](concurrency-direct3d-namespace-functions-amp.md#mad)|Fazla Yüklendi. Bir üç bağımsız değişken üzerinde aritmetik çarpma/ekleme işlemi gerçekleştirir: _X \* _Y + _Z|
|[make_array](concurrency-direct3d-namespace-functions-amp.md#make_array)|Bir D3D arabellek arayüz işaretçisinden bir dizi oluşturun.|
|[gürültü](concurrency-direct3d-namespace-functions-amp.md#noise)|Perlin gürültü algoritmasını kullanarak rastgele bir değer oluşturur.|
|[radyan cinsinden](concurrency-direct3d-namespace-functions-amp.md#radians)|_X'i dereceden radyana çevirir.|
|[rcp](concurrency-direct3d-namespace-functions-amp.md#rcp)|Bağımsız değişkenin hızlı, yaklaşık tersini hesaplar|
|[reversebits](concurrency-direct3d-namespace-functions-amp.md#reversebits)|_X'deki bitlerin sırasını tersine çevirir|
|[Saturate](concurrency-direct3d-namespace-functions-amp.md#saturate)|0 ile 1 aralığında _x'i sıkıştırır.|
|[sign](concurrency-direct3d-namespace-functions-amp.md#sign)|Fazla Yüklendi. Bağımsız değişkenin işaretini döndürür|
|[smoothstep](concurrency-direct3d-namespace-functions-amp.md#smoothstep)|_X [_Min, _Max] aralığında ise, 0 ile 1 arasında düzgün bir Hermite enterpolasyon döndürür.|
|[Adım](concurrency-direct3d-namespace-functions-amp.md#step)|İki değer, 0 veya 1 hangi değerin daha büyük olduğuna göre karşılaştırır.|
|[umax](concurrency-direct3d-namespace-functions-amp.md#umax)|Büyük bir değer döndüren işaretsiz iki değeri karşılaştırır.|
|[umin](concurrency-direct3d-namespace-functions-amp.md#umin)|Daha küçük olan bir değer döndüren işaretsiz iki değeri karşılaştırır.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** amp.h

**Namespace:** eşzamanlılık

## <a name="see-also"></a>Ayrıca Bkz.

[Eşzamanlılık Ad Alanı (C++ AMP)](concurrency-namespace-cpp-amp.md)
