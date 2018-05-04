---
title: _Crtısvalidpointer | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _CrtIsValidPointer
apilocation:
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
apitype: DLLExport
f1_keywords:
- CrtlsValidPointer
- _CrtIsValidPointer
dev_langs:
- C++
helpviewer_keywords:
- CrtIsValidPointer function
- _CrtIsValidPointer function
ms.assetid: 91c35590-ea5e-450f-a15d-ad8d62ade1fa
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1bb78f8dee494fd213df6db16e2800cb9090bdf3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="crtisvalidpointer"></a>_CrtIsValidPointer

Bir işaretçi null olmadığını doğrular. C çalışma zamanı kitaplığı Visual Studio 2010 önce sürümlerinde, belirtilen bellek aralığı okuma ve yazma (yalnızca hata ayıklama sürümü) için geçerli olduğunu doğrular.

## <a name="syntax"></a>Sözdizimi

```C
int _CrtIsValidPointer(
   const void *address,
   unsigned int size,
   int access
);
```

### <a name="parameters"></a>Parametreler

*Adres*<br/>
Başlangıç noktalarına geçerliliğini sınamak için bellek aralığının.

*Boyutu*<br/>
Boyutu (bayt cinsinden) belirtilen bellek aralığının.

*Erişim*<br/>
Bellek aralığı belirlemek için okuma/yazma erişilebilirlik.

## <a name="return-value"></a>Dönüş Değeri

**_Crtısvalidpointer** belirtilen işaretçisi null değil varsa TRUE değerini döndürür. Visual Studio 2010 önce CRT kitaplık sürümleri bellek aralığı belirtilen işlem veya işlemleri için geçerli ise TRUE değerini döndürür. Aksi takdirde işlevi FALSE değerini döndürür.

## <a name="remarks"></a>Açıklamalar

Visual Studio 2010 CRT kitaplık başlayarak *boyutu* ve *erişim* parametreleri yoksayılır ve **_crtısvalidpointer** yalnızca doğrular belirtilen *adresi* null değil. Bu test kendiniz gerçekleştirmek kolay olduğundan, bu işlevi kullanmak önerilmez. Visual Studio 2010 önce sürümlerde başlangıç bellek aralığı doğrular işlevi *adresi* ve için genişletme *boyutu* bayttır belirtilen erişilebilirlik işlemi veya işlemleri için geçerli. Zaman *erişim* olan TRUE olarak ayarlanırsa, hem okuma ve yazma için bellek aralığı doğrulanır. Zaman *erişim* false, bellek aralığı yalnızca okuma için doğrulanır. Zaman [_DEBUG](../../c-runtime-library/debug.md) tanımlı değil, çağrılar **_crtısvalidpointer** ön işleme sırasında kaldırılır.

Bu işlev TRUE veya false değeri döndürdüğünden, aşağıdakilerden birini geçirilebilir [_ASSERT](assert-asserte-assert-expr-macros.md) makroları işleme mekanizması basit bir hata ayıklama hata oluştur. Bellek aralığı hem okuma hem de yazma işlemleri için geçerli değilse, aşağıdaki örnekte bir onaylama işlemi hatasına neden olur:

```C
_ASSERTE( _CrtIsValidPointer( address, size, TRUE ) );
```

Hakkında daha fazla bilgi için **_crtısvalidpointer** diğer hata ayıklama işlevleri ve makrolar kullanılabilmesi için bkz: [raporlama makroları](/visualstudio/debugger/macros-for-reporting). Nasıl bellek blokları ayrılmış, başlatılmış ve temel yığın hata ayıklama sürümü yönetilen hakkında daha fazla bilgi için bkz: [CRT hata ayıklama öbeği ayrıntıları](/visualstudio/debugger/crt-debug-heap-details).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_CrtIsValidPointer**|\<crtdbg.h >|

**_Crtısvalidpointer** bir Microsoft uzantısıdır. Uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Hata ayıklama sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md) yalnızca.

## <a name="example"></a>Örnek

Örneğin bkz [_crtısvalidheappointer](crtisvalidheappointer.md) konu.

## <a name="see-also"></a>Ayrıca bkz.

[Hata Ayıklama Yordamları](../../c-runtime-library/debug-routines.md)<br/>
