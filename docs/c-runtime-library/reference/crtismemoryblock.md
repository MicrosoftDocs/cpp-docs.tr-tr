---
title: _Crtısmemoryblock | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _CrtIsMemoryBlock
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
- CrtlsMemoryBlock
- _CrtIsMemoryBlock
dev_langs:
- C++
helpviewer_keywords:
- _CrtIsMemoryBlock function
- CrtIsMemoryBlock function
ms.assetid: f7cbbc60-3690-4da0-a07b-68fd7f250273
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dee3e30e5bde5a3bed67d975c96b00568306f926
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="crtismemoryblock"></a>_CrtIsMemoryBlock

Belirtilen bellek bloğu içinde yerel yığın olduğunu ve bir geçerli hata ayıklama yığını blok türü tanımlayıcısı'nı (yalnızca hata ayıklama sürümü) sahip olduğunu doğrular.

## <a name="syntax"></a>Sözdizimi

```C
int _CrtIsMemoryBlock(
   const void *userData,
   unsigned int size,
   long *requestNumber,
   char **filename,
   int *linenumber
);
```

### <a name="parameters"></a>Parametreler

*UserData*<br/>
İşaretçi doğrulamak için bellek bloğu başlangıcına.

*Boyutu*<br/>
Boyutu belirtilen bloğun (bayt cinsinden).

*requestNumber*<br/>
İşaretçi blok ayırma sayısına veya **NULL**.

*Dosya adı*<br/>
İşaretçi blok istenen kaynak dosya adını veya **NULL**.

*LineNumber*<br/>
Kaynak dosyasında satır numarası işaretçi veya **NULL**.

## <a name="return-value"></a>Dönüş Değeri

**_Crtısmemoryblock** döndürür **TRUE** belirtilen bellek bloğu yerel yığın içinde bulunur ve geçerli hata ayıklama yığını blok türü tanımlayıcısı; Aksi halde, işlevi döndürür **FALSE**.

## <a name="remarks"></a>Açıklamalar

**_Crtısmemoryblock** işlevi, belirtilen bellek bloğu uygulamanın yerel yığın içinde bulunur ve geçerli blok türü tanımlayıcısı sahip olduğunu doğrular. Bu işlev, burada bellek bloğu ayırma başlangıçta istenen nesne ayırma sipariş numarası ve kaynak dosya adı/satır numarasını almak için de kullanılabilir. NULL olmayan değerler geçirmesi *requestNumber*, *filename*, veya *linenumber* parametreleri nedenler **_crtısmemoryblock** ayarlamak için yerel yığın blok bulursa, bu parametreler bellek bloğun değerler başlığı, hata ayıklama. Zaman [_DEBUG](../../c-runtime-library/debug.md) tanımlı değil, çağrılar **_crtısmemoryblock** ön işleme sırasında kaldırılır.

Varsa **_crtısmemoryblock** başarısız, döndürdüğü **FALSE** ve çıkış parametreleri varsayılan değerlere başlatılır: *requestNumber* ve **lineNumber**  0 olarak ayarlayın ve *filename* ayarlanır **NULL**.

Bu işlev döndürdüğünden **TRUE** veya **FALSE**, onu biri olarak geçirilebilir [_ASSERT](assert-asserte-assert-expr-macros.md) makroları işleme mekanizması basit bir hata ayıklama hata oluştur. Belirtilen adres yerel yığın içinde bulunduğu değilse, aşağıdaki örnekte bir onaylama işlemi hatasına neden olur:

```C
_ASSERTE( _CrtIsMemoryBlock( userData, size, &requestNumber,
          &filename, &linenumber ) );
```

Hakkında daha fazla bilgi için **_crtısmemoryblock** diğer hata ayıklama işlevleri ve makrolar kullanılabilmesi için bkz: [raporlama makroları](/visualstudio/debugger/macros-for-reporting). Nasıl bellek blokları ayrılmış, başlatılmış ve temel yığın hata ayıklama sürümü yönetilen hakkında daha fazla bilgi için bkz: [CRT hata ayıklama öbeği ayrıntıları](/visualstudio/debugger/crt-debug-heap-details).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_CrtIsMemoryBlock**|\<crtdbg.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Hata ayıklama sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md) yalnızca.

## <a name="example"></a>Örnek

Örneğin bkz [_crtısvalidheappointer](crtisvalidheappointer.md) konu.

## <a name="see-also"></a>Ayrıca bkz.

[Hata Ayıklama Yordamları](../../c-runtime-library/debug-routines.md)<br/>
