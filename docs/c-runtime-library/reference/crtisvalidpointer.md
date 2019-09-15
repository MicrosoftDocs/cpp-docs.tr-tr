---
title: _CrtIsValidPointer
ms.date: 11/04/2016
api_name:
- _CrtIsValidPointer
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
- CrtlsValidPointer
- _CrtIsValidPointer
helpviewer_keywords:
- CrtIsValidPointer function
- _CrtIsValidPointer function
ms.assetid: 91c35590-ea5e-450f-a15d-ad8d62ade1fa
ms.openlocfilehash: 490d2dea097935dee2cd2a003aa28e32f1ced69d
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70938779"
---
# <a name="_crtisvalidpointer"></a>_CrtIsValidPointer

Bir işaretçinin null olmadığını doğrular. Visual Studio 2010 ' den önceki C çalışma zamanı kitaplığı sürümlerinde, belirtilen bir bellek aralığının okuma ve yazma için geçerli olduğunu doğrular (yalnızca hata ayıklama sürümü).

## <a name="syntax"></a>Sözdizimi

```C
int _CrtIsValidPointer(
   const void *address,
   unsigned int size,
   int access
);
```

### <a name="parameters"></a>Parametreler

*adrestir*<br/>
Geçerliliği sınamak için bellek aralığının başlangıcını gösterir.

*boyutla*<br/>
Belirtilen bellek aralığının boyutu (bayt).

*erişmesini*<br/>
Bellek aralığını öğrenmek için okuma/yazma erişilebilirliği.

## <a name="return-value"></a>Dönüş Değeri

**_Crtisvalidpointer** , belirtilen işaretçi null değilse true değerini döndürür. Visual Studio 2010 ' den önceki CRT kitaplık sürümlerinde, bellek aralığı belirtilen işlem veya işlemler için geçerliyse TRUE değerini döndürür. Aksi takdirde, işlev FALSE döndürür.

## <a name="remarks"></a>Açıklamalar

Visual Studio 2010 ' deki CRT kitaplığı ile başlayarak, *Boyut* ve *erişim* parametreleri yok sayılır ve **_crtisvalidpointer** yalnızca belirtilen *adresin* null olmadığını doğrular. Bu testin kolayca gerçekleştirilebilmesi için, bu işlevi kullanmanızı önermiyoruz. Visual Studio 2010 ' den önceki sürümlerde işlev, *adreste* başlayan ve *Boyut* baytları için genişleyen bellek aralığının belirtilen erişilebilirlik işlemi veya işlemler için geçerli olduğunu doğrular. *ERIŞIM* doğru olarak ayarlandığında, bellek aralığı hem okuma hem de yazma için doğrulanır. *ERIŞIM* false olduğunda, bellek aralığı yalnızca okuma için onaylanır. [_Hata ayıklama](../../c-runtime-library/debug.md) tanımlanmadığında, **_Crtisvalidpointer** çağrısı, ön işleme sırasında kaldırılır.

Bu işlev TRUE veya FALSE döndürdüğünden, basit bir hata ayıklama hata işleme mekanizması oluşturmak için [_Onaylama](assert-asserte-assert-expr-macros.md) makrolarından birine geçirilebilir. Aşağıdaki örnek, bellek aralığı hem okuma hem de yazma işlemleri için geçerli değilse bir onaylama hatasına neden olur:

```C
_ASSERTE( _CrtIsValidPointer( address, size, TRUE ) );
```

**_Crtisvalidpointer** 'ın diğer hata ayıklama işlevleri ve makroları ile nasıl kullanılabileceği hakkında daha fazla bilgi için bkz: [Raporlama makroları](/visualstudio/debugger/macros-for-reporting). Bellek bloklarının taban yığının hata ayıklama sürümünde nasıl ayrıldığı, başlatıldığı ve yönetildiği hakkında bilgi için bkz. [CRT hata ayıklama yığını ayrıntıları](/visualstudio/debugger/crt-debug-heap-details).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_CrtIsValidPointer**|\<Crtdbg. h >|

**_Crtisvalidpointer** bir Microsoft uzantısıdır. Uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Yalnızca [C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md) sürümlerini ayıklayın.

## <a name="example"></a>Örnek

[_Crtısvalidheappointer](crtisvalidheappointer.md) konusunun örneğine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Hata Ayıklama Yordamları](../../c-runtime-library/debug-routines.md)<br/>
