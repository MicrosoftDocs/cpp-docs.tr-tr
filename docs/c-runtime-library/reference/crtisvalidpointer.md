---
title: _CrtIsValidPointer
ms.date: 11/04/2016
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
helpviewer_keywords:
- CrtIsValidPointer function
- _CrtIsValidPointer function
ms.assetid: 91c35590-ea5e-450f-a15d-ad8d62ade1fa
ms.openlocfilehash: 64197d460cdb7dd26d22196c08151be09df48573
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50429264"
---
# <a name="crtisvalidpointer"></a>_CrtIsValidPointer

Bir işaretçi null olmadığını doğrular. Visual Studio 2010 önce C çalışma zamanı kitaplığı sürümlerinde, belirtilen bellek aralığının okuma ve yazma (yalnızca hata ayıklama sürümü) için geçerli olduğunu doğrular.

## <a name="syntax"></a>Sözdizimi

```C
int _CrtIsValidPointer(
   const void *address,
   unsigned int size,
   int access
);
```

### <a name="parameters"></a>Parametreler

*Adresi*<br/>
Geçerliliğini sınamak için bellek aralığının başlangıç noktalarına.

*Boyutu*<br/>
Boyut (bayt cinsinden) belirtilen bellek aralığının.

*Erişim*<br/>
Bellek aralığı belirlemek için okuma/yazma erişilebilirlik.

## <a name="return-value"></a>Dönüş Değeri

**_Crtısvalidpointer** belirtilen işaretçi boş değilse true değer döndürür. Visual Studio 2010 önce CRT kitaplık sürümleri bellek aralığın belirtilen işlemin veya işlemlerin için geçerli ise TRUE değerini döndürür. Aksi takdirde işlev false değerini döndürür.

## <a name="remarks"></a>Açıklamalar

CRT Kitaplığı Visual Studio 2010 ile başlayarak *boyutu* ve *erişim* parametreleri yok sayılır ve **_crtısvalidpointer** doğrular yalnızca belirtilen *adresi* null değil. Bu test kendiniz yapmak çok kolay olduğundan, bu işlevi kullanmak önerilmez. Visual Studio 2010 önce sürümlerinde konumunda başlayan bellek aralığı doğrular işlevi *adresi* ve için genişletme *boyutu* bayttır belirtilen erişilebilirlik işlemin veya işlemlerin için geçerli. Zaman *erişim* olan TRUE olarak ayarlanırsa, hem okuma ve yazma için bellek aralığı doğrulanır. Zaman *erişim* yanlış, bellek aralığı yalnızca okuma için doğrulanır. Zaman [_DEBUG](../../c-runtime-library/debug.md) tanımlı değil, çağrılar **_crtısvalidpointer** ön işleme sırasında kaldırılır.

Bu işlev, TRUE veya false değeri döndürdüğünden, onu birine geçirilebilir [_ASSERT](assert-asserte-assert-expr-macros.md) makroları basit bir hata ayıklama hata işleme mekanizması oluşturmak için. Bellek aralığın hem okuma hem de yazma işlemleri için geçerli değilse, aşağıdaki örnekte bir onaylama işlemi hatasına neden olur:

```C
_ASSERTE( _CrtIsValidPointer( address, size, TRUE ) );
```

Hakkında daha fazla bilgi için **_crtısvalidpointer** diğer hata ayıklama işlevlerini ve makrolarını birlikte kullanılabilir, bkz: [raporlama için makroları](/visualstudio/debugger/macros-for-reporting). Nasıl bellek blokları ayrılan, başlatılır ve taban yığının hata ayıklama sürümünde yönetilen hakkında daha fazla bilgi için bkz: [CRT hata ayıklama öbeği ayrıntıları](/visualstudio/debugger/crt-debug-heap-details).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_CrtIsValidPointer**|\<crtdbg.h >|

**_Crtısvalidpointer** bir Microsoft uzantısıdır. Uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Hata ayıklama sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md) yalnızca.

## <a name="example"></a>Örnek

Örneğin bakın [_crtısvalidheappointer](crtisvalidheappointer.md) konu.

## <a name="see-also"></a>Ayrıca bkz.

[Hata Ayıklama Yordamları](../../c-runtime-library/debug-routines.md)<br/>
