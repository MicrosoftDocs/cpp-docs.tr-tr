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
ms.openlocfilehash: e1374acbd7061afaba372100cf6e69d9d717da8a
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77127039"
---
# <a name="concurrencydirect3d-namespace"></a>Concurrency::direct3d Ad Alanı

`direct3d` ad alanı, D3D birlikte çalışabilirliği destekleyen işlevler sağlar. Bu, AMP kodunda işlem için D3D kaynaklarını kullanmanıza olanak sağlar. Ayrıca, yedekli ara kopyalar oluşturmadan D3D kodunda AMP 'da oluşturulan kaynakların kullanılmasına de olanak tanır. Amp kullanarak C++ DirectX uygulamalarınızın yoğun işlem yoğunluğu bölümlerini artımlı olarak HıZLANDıRABILIR ve amp hesaplamalarından ÜRETILEN VERILERDE D3D API 'sini kullanabilirsiniz.

## <a name="syntax"></a>Sözdizimi

```cpp
namespace direct3d;
```

## <a name="members"></a>Üyeler

### <a name="classes"></a>Sınıflar

|Ad|Açıklama|
|----------|-----------------|
|[scoped_d3d_access_lock Sınıfı](scoped-d3d-access-lock-class.md)|Bir `accelerator_view` nesnesi üzerinde D3D erişim kilidi için bir ÇII sarmalayıcı.|

### <a name="structures"></a>Yapılar

|Ad|Açıklama|
|----------|-----------------|
|[adopt_d3d_access_lock_t Yapısı](adopt-d3d-access-lock-t-structure.md)|D3D erişim kilidinin alım yerine benimsemesi gerektiğini belirten etiket türü.|

### <a name="functions"></a>İşlevler

|Ad|Açıklama|
|----------|-----------------|
|[mutlak](concurrency-direct3d-namespace-functions-amp.md#abs)|Bağımsız değişkenin mutlak değerini döndürür|
|[Clamp](concurrency-direct3d-namespace-functions-amp.md#clamp)|Fazla Yüklendi. Clamps 'ler Belirtilen _Min ve _Max aralığına _X|
|[countbits](concurrency-direct3d-namespace-functions-amp.md#countbits)|_X içindeki küme bitlerinin sayısını sayar|
|[create_accelerator_view](concurrency-direct3d-namespace-functions-amp.md#create_accelerator_view)|Direct3D cihaz arabirimine yönelik bir işaretçiden bir [accelerator_view sınıfı](accelerator-view-class.md) oluşturur|
|[d3d_access_lock](concurrency-direct3d-namespace-functions-amp.md#d3d_access_lock)|Accelerator_view paylaşılan kaynaklarda güvenli bir şekilde D3D işlemleri gerçekleştirmek için accelerator_view bir kilit alır|
|[d3d_access_try_lock](concurrency-direct3d-namespace-functions-amp.md#d3d_access_try_lock)|Blok olmadan bir accelerator_view D3D erişim kilidi alma girişimi.|
|[d3d_access_unlock](concurrency-direct3d-namespace-functions-amp.md#d3d_access_unlock)|Belirtilen accelerator_view D3D erişim kilidini serbest bırakın.|
|[firstbithigh](concurrency-direct3d-namespace-functions-amp.md#firstbithigh)|En yüksek sıra bitden başlayıp aşağı doğru çalışma _X, ilk küme bitinin konumunu alır.|
|[firstbitlow](concurrency-direct3d-namespace-functions-amp.md#firstbitlow)|En düşük sıra bitden başlayıp yukarı doğru çalışarak _X ilk küme bitinin konumunu alır|
|[get_buffer](concurrency-direct3d-namespace-functions-amp.md#get_buffer)|Bir diziyi temel alan D3D arabellek arabirimini alın.|
|[IMAX](concurrency-direct3d-namespace-functions-amp.md#imax)|Daha büyük değer döndüren iki değeri karşılaştırır.|
|[imin](concurrency-direct3d-namespace-functions-amp.md#imin)|, Daha küçük değer döndüren iki değeri karşılaştırır.|
|[is_timeout_disabled](concurrency-direct3d-namespace-functions-amp.md#is_timeout_disabled)|Belirtilen accelerator_view için zaman aşımının devre dışı bırakılıp bırakılmadığını belirten bir Boole bayrağı döndürür.|
|[Mad](concurrency-direct3d-namespace-functions-amp.md#mad)|Fazla Yüklendi. Üç bağımsız değişken üzerinde aritmetik çarpma/ekleme işlemi gerçekleştirir: _X \* _Y + _Z|
|[make_array](concurrency-direct3d-namespace-functions-amp.md#make_array)|D3D arabellek arabirim işaretçisinden bir dizi oluşturun.|
|[gürültü](concurrency-direct3d-namespace-functions-amp.md#noise)|Perlin gürültü algoritmasını kullanarak rastgele bir değer üretir|
|[radyan](concurrency-direct3d-namespace-functions-amp.md#radians)|_X dereceden radyana dönüştürür|
|[rcp](concurrency-direct3d-namespace-functions-amp.md#rcp)|Bağımsız değişkeninin hızlı ve yaklaşık bir tersini hesaplar|
|[reversebits](concurrency-direct3d-namespace-functions-amp.md#reversebits)|_X içindeki bitlerin sırasını tersine çevirir|
|[saturate](concurrency-direct3d-namespace-functions-amp.md#saturate)|Clamps, 0 ile 1 arasında _X|
|[sign](concurrency-direct3d-namespace-functions-amp.md#sign)|Fazla Yüklendi. Bağımsız değişkenin işaretini döndürür|
|[smoothstep](concurrency-direct3d-namespace-functions-amp.md#smoothstep)|_X [_Min, _Max] aralığalıyorsa, 0 ile 1 arasında yumuşak bir Hermite ilişkilendirmeyi döndürür.|
|[ından](concurrency-direct3d-namespace-functions-amp.md#step)|İki değeri karşılaştırır; 0 veya 1 döndüren değerin daha büyük olması gerekir|
|['ın](concurrency-direct3d-namespace-functions-amp.md#umax)|İki işaretsiz değeri karşılaştırır ve daha büyük değer döndürür.|
|[umın](concurrency-direct3d-namespace-functions-amp.md#umin)|Daha küçük olan değeri döndüren iki işaretsiz değeri karşılaştırır.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** amp. h

**Ad alanı:** Zamanlı

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı (C++ AMP)](concurrency-namespace-cpp-amp.md)
