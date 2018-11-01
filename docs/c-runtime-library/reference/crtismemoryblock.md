---
title: _CrtIsMemoryBlock
ms.date: 11/04/2016
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
helpviewer_keywords:
- _CrtIsMemoryBlock function
- CrtIsMemoryBlock function
ms.assetid: f7cbbc60-3690-4da0-a07b-68fd7f250273
ms.openlocfilehash: c4a85ebeb45552c6f5355853de2a45766d6bc984
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50555773"
---
# <a name="crtismemoryblock"></a>_CrtIsMemoryBlock

Belirtilen bellek bloğu yerel yığında olduğunu ve bir geçerli hata ayıklama yığın blok türü tanımlayıcısı'nı (yalnızca hata ayıklama sürümü) sahip olduğunu doğrular.

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

*userData*<br/>
Doğrulamak için bellek bloğu başlangıcı için işaretçi.

*Boyutu*<br/>
(Bayt cinsinden) belirtilen blok boyutu.

*requestNumber*<br/>
Blok ayırma sayısını işaretçisi veya **NULL**.

*Dosya adı*<br/>
Blok istenen kaynak dosyasının adını işaretçisi veya **NULL**.

*LineNumber*<br/>
Kaynak dosyadaki satır numarası işaretçi veya **NULL**.

## <a name="return-value"></a>Dönüş Değeri

**_Crtısmemoryblock** döndürür **TRUE** belirtilen bellek bloğu yerel yığın içinde bulunur ve geçerli hata ayıklama yığın blok türü tanımlayıcısı; Aksi halde, işlev döndürür **FALSE**.

## <a name="remarks"></a>Açıklamalar

**_Crtısmemoryblock** işlevi, belirtilen bellek bloğu uygulamanın yerel yığın içinde bulunur ve geçerli blok türü tanımlayıcısı sahip olduğunu doğrular. Bu işlev, nesne ayırma sipariş numarası ve dosya adı/satır numarasını bellek bloğu ayırma başlangıçta istenen burada elde etmek için de kullanılabilir. Geçirme olmayan**NULL** değerleri *requestNumber*, *filename*, veya *linenumber* parametreleri nedenleri **_ Crtısmemoryblock** yerel yığında blok bulursa bellek bloğun hata ayıklama üstbilgi değerleri için bu parametreleri ayarlamak için. Zaman [_DEBUG](../../c-runtime-library/debug.md) tanımlı değil, çağrılar **_crtısmemoryblock** ön işleme sırasında kaldırılır.

Varsa **_crtısmemoryblock** döndürür, başarısız **FALSE** ve çıkış parametrelerini varsayılan değerlerine başlatılır: *requestNumber* ve **lineNumber**  0 olarak ayarlayın ve *filename* ayarlanır **NULL**.

Bu işlev döndürdüğü için **TRUE** veya **FALSE**, onu birine geçirilebilir [_ASSERT](assert-asserte-assert-expr-macros.md) makroları basit bir hata ayıklama hata işleme mekanizması oluşturmak için. Belirtilen adres yerel yığında yer değilse, aşağıdaki örnekte bir onaylama işlemi hatasına neden olur:

```C
_ASSERTE( _CrtIsMemoryBlock( userData, size, &requestNumber,
          &filename, &linenumber ) );
```

Hakkında daha fazla bilgi için **_crtısmemoryblock** diğer hata ayıklama işlevlerini ve makrolarını birlikte kullanılabilir, bkz: [raporlama için makroları](/visualstudio/debugger/macros-for-reporting). Nasıl bellek blokları ayrılan, başlatılır ve taban yığının hata ayıklama sürümünde yönetilen hakkında daha fazla bilgi için bkz: [CRT hata ayıklama öbeği ayrıntıları](/visualstudio/debugger/crt-debug-heap-details).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_CrtIsMemoryBlock**|\<crtdbg.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Hata ayıklama sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md) yalnızca.

## <a name="example"></a>Örnek

Örneğin bakın [_crtısvalidheappointer](crtisvalidheappointer.md) konu.

## <a name="see-also"></a>Ayrıca bkz.

[Hata Ayıklama Yordamları](../../c-runtime-library/debug-routines.md)<br/>
