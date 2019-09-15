---
title: _CrtDumpMemoryLeaks
ms.date: 11/04/2016
api_name:
- _CrtDumpMemoryLeaks
api_location:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- CRTDBG_LEAK_CHECK_DF
- CRTDBG_CHECK_CRT_DF
- _CRTDBG_LEAK_CHECK_DF
- CrtDumpMemoryLeaks
- _CrtDumpMemoryLeaks
- _CRTDBG_CHECK_CRT_DF
helpviewer_keywords:
- CrtDumpMemoryLeaks function
- CRTDBG_LEAK_CHECK_DF macro
- _CRTDBG_LEAK_CHECK_DF macro
- _CrtDumpMemoryLeaks function
- CRTDBG_CHECK_CRT_DF macro
- _CRTDBG_CHECK_CRT_DF macro
ms.assetid: 71b2eab4-7f55-44e8-a55a-bfea4f32d34c
ms.openlocfilehash: dae93577f5c0c0297606577c05d6b6ef2040c831
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70938825"
---
# <a name="_crtdumpmemoryleaks"></a>_CrtDumpMemoryLeaks

Bellek sızıntısı oluştuğunda hata ayıklama yığınındaki tüm bellek bloklarını döker (yalnızca hata ayıklama sürümü).

## <a name="syntax"></a>Sözdizimi

```C

int _CrtDumpMemoryLeaks( void );
```

## <a name="return-value"></a>Dönüş Değeri

**_Crtdumpmemorysızıntı** , bir bellek sızıntısı bulunursa doğru döndürür. Aksi takdirde, işlev FALSE döndürür.

## <a name="remarks"></a>Açıklamalar

**_Crtdumpmemorysızıntı** işlevi, program yürütme başlangıcından bu yana bir bellek sızıntısı oluşup oluşmadığını belirler. Bir sızıntı bulunduğunda, yığındaki tüm nesneler için hata ayıklama üstbilgi bilgileri Kullanıcı tarafından okunabilen bir biçimde dökülür. [_Hata ayıklama](../../c-runtime-library/debug.md) tanımlanmadığında, **_Crtdumpmemorysızıntı** çağrısı, ön işleme sırasında kaldırılır.

**_Crtdumpmemorysızıntı** , uygulama tarafından ayrılan tüm belleğin serbest olduğunu doğrulamak için genellikle program yürütmenin sonunda çağırılır. İşlevi, [_Crtsetdbgflag](crtsetdbgflag.md) işlevi kullanılarak _Crtdbgflag bayrağının **_Crtdbg_liak_check_df** bit [](../../c-runtime-library/crtdbgflag.md) alanını etkinleştirerek program sonlandırmada otomatik olarak çağrılabilir.

**_Crtdumpmemorysızıntı** , yığının geçerli durumunu almak Için [_Crtmemcheckpoint](crtmemcheckpoint.md) çağırır ve sonra serbest bırakılmamış blokların durumunu tarar. Serbest bırakılmamış bir blokta karşılaşıldığında, **_Crtdumpmemorysızıntı** , program yürütme başlangıcından yığında ayrılan tüm nesneler için döküm bilgilerini [_CrtMemDumpAllObjectsSince](crtmemdumpallobjectssince.md) çağırır.

Varsayılan olarak, iç C çalışma zamanı blokları ( **_CRT_BLOCK**) bellek dökümü işlemlerine dahil edilmez. [_Crtsetdbgflag](crtsetdbgflag.md) işlevi, sızıntı algılama sürecinde bu blokları dahil etmek Için **_Crtdbgflag** 'ın **_CRTDBG_CHECK_CRT_DF** bitini açmak üzere kullanılabilir.

Yığın durumu işlevleri ve **_Crtmemstate** yapısı hakkında daha fazla bilgi için bkz. [yığın durum raporlama işlevleri](/visualstudio/debugger/crt-debug-heap-details). Bellek bloklarının taban yığının hata ayıklama sürümünde nasıl ayrıldığı, başlatıldığı ve yönetildiği hakkında daha fazla bilgi için bkz. [CRT hata ayıklama yığını ayrıntıları](/visualstudio/debugger/crt-debug-heap-details).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_CrtDumpMemoryLeaks**|\<Crtdbg. h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Yalnızca [C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md) sürümlerini ayıklayın.

## <a name="example"></a>Örnek

**_Crtdumpmemorysızıntısına**nasıl kullanacağınızı gösteren bir örnek için bkz. [crt_dbg1](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg1).

## <a name="see-also"></a>Ayrıca bkz.

[Hata Ayıklama Yordamları](../../c-runtime-library/debug-routines.md)<br/>
