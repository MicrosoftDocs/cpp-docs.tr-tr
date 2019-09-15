---
title: _CrtIsMemoryBlock
ms.date: 11/04/2016
api_name:
- _CrtIsMemoryBlock
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
- CrtlsMemoryBlock
- _CrtIsMemoryBlock
helpviewer_keywords:
- _CrtIsMemoryBlock function
- CrtIsMemoryBlock function
ms.assetid: f7cbbc60-3690-4da0-a07b-68fd7f250273
ms.openlocfilehash: f29745acd06f6f5b3fa96367444e800bdc3e8e3a
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70938734"
---
# <a name="_crtismemoryblock"></a>_CrtIsMemoryBlock

Belirtilen bir bellek bloğunun yerel yığında olduğunu ve geçerli bir hata ayıklama yığını blok türü tanımlayıcısına sahip olduğunu doğrular (yalnızca hata ayıklama sürümü).

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
Doğrulanacak bellek bloğunun başlangıcına yönelik işaretçi.

*boyutla*<br/>
Belirtilen bloğun boyutu (bayt).

*requestNumber*<br/>
Bloğun veya **null**ayırma numarası işaretçisi.

*kısaltın*<br/>
Bloğu veya **null değerini**isteyen kaynak dosyanın adı işaretçisi.

*onayın*<br/>
Kaynak dosyadaki satır numarası işaretçisi veya **null**.

## <a name="return-value"></a>Dönüş Değeri

**_Crtismemoryblock** , belirtilen bellek bloğu yerel yığında bulunuyorsa ve geçerli bir hata ayıklama yığın blok türü tanımlayıcısına sahipse **true** değerini döndürür; Aksi takdirde, işlev **false**döndürür.

## <a name="remarks"></a>Açıklamalar

**_Crtımemoryblock** işlevi, belirtilen bir bellek bloğunun uygulamanın yerel yığınında bulunduğunu ve geçerli bir blok türü tanımlayıcısına sahip olduğunu doğrular. Bu işlev, nesne ayırma sıra numarasını ve bellek bloğu ayırmanın ilk olarak istediği kaynak dosya adı/satır numarasını almak için de kullanılabilir. *RequestNumber*, *filename*veya *onayın* parametrelerinin**null** olmayan değerlerini geçirme, **_crtismemoryblock** 'in, blok içindeki bu parametreleri bellek bloğunun hata ayıklama üstbilgisindeki değerlere almasına neden olur. yerel yığın. [_Hata ayıklama](../../c-runtime-library/debug.md) tanımlanmadığında, **_Crtismemoryblock** çağrıları ön işleme sırasında kaldırılır.

**_Crtismemoryblock** başarısız olursa, **false** döndürür ve çıkış parametreleri varsayılan değerlere başlatılır: *requestNumber* ve **LineNumber** , 0 olarak ayarlanır ve *filename* **null**olarak ayarlanır.

Bu işlev **true** veya **false**döndürdüğünden, basit bir hata ayıklama hata Işleme mekanizması oluşturmak için [_onaylama](assert-asserte-assert-expr-macros.md) makrolarından birine geçirilebilir. Aşağıdaki örnek, belirtilen adres yerel yığında bulunmuyorsa bir onaylama hatasına neden olur:

```C
_ASSERTE( _CrtIsMemoryBlock( userData, size, &requestNumber,
          &filename, &linenumber ) );
```

**_Crtılationmemoryblock** diğer hata ayıklama işlevleriyle ve makrolarıyla nasıl kullanılabileceği hakkında daha fazla bilgi için bkz: [Raporlama makroları](/visualstudio/debugger/macros-for-reporting). Bellek bloklarının taban yığının hata ayıklama sürümünde nasıl ayrıldığı, başlatıldığı ve yönetildiği hakkında bilgi için bkz. [CRT hata ayıklama yığını ayrıntıları](/visualstudio/debugger/crt-debug-heap-details).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_CrtIsMemoryBlock**|\<Crtdbg. h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Yalnızca [C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md) sürümlerini ayıklayın.

## <a name="example"></a>Örnek

[_Crtısvalidheappointer](crtisvalidheappointer.md) konusunun örneğine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Hata Ayıklama Yordamları](../../c-runtime-library/debug-routines.md)<br/>
