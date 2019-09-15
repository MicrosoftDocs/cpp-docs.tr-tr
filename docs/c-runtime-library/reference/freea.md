---
title: _freea
ms.date: 11/04/2016
api_name:
- _freea
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
- freea
- _freea
helpviewer_keywords:
- _freea function
- freea function
- memory deallocation
ms.assetid: dcd30584-dd9d-443b-8c4c-13237a1cecac
ms.openlocfilehash: dcad8bea4f8cec28d8cb15a9937b1032593ef0cc
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70956718"
---
# <a name="_freea"></a>_freea

Bellek bloğunu ayırır veya serbest bırakır.

## <a name="syntax"></a>Sözdizimi

```C
void _freea(
   void *memblock
);
```

### <a name="parameters"></a>Parametreler

*memblock*<br/>
Serbest bırakmak için önceden ayrılmış bellek bloğu.

## <a name="return-value"></a>Dönüş Değeri

Yok.

## <a name="remarks"></a>Açıklamalar

**_Freea** işlevi, daha önce [_malloca](malloca.md)çağrısıyla ayrılmış bir bellek bloğunu (*memblock*) ayırır. **_freea** , belleğin yığında mi yoksa yığında mi ayrıldığını görmek için denetler. Yığında ayrıldıysa, **_freea** hiçbir şey yapmaz. Yığın üzerinde ayrıldıysa, serbest bırakılan bayt sayısı, blok ayrıldığında istenen bayt sayısına eşittir. *Memblock* **null**ise, işaretçi yok sayılır ve **_freea** hemen döndürülür. Geçersiz bir işaretçi serbest bırakma girişimi ( **_malloca**tarafından ayrılmamış bir bellek bloğunun işaretçisi) sonraki ayırma isteklerini etkileyebilir ve hatalara neden olabilir.

**_freea** çağrısı, belleğin yığında ayrıldığını bulursa dahili olarak **ücretsiz** bir çağrı. Belleğin yığında olup olmadığı ya da yığının, ayrılmış bellekten hemen önceki adresteki belleğe yerleştirilmiş bir işaretleyici tarafından belirlenir.

Belleği boşaltmaya yönelik bir hata oluşursa, **errno** , işletim sisteminden hata doğasından bilgi olarak ayarlanır. Daha fazla bilgi için bkz. [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Bellek bloğu serbest bırakıldıktan sonra, [_heapmin](heapmin.md) kullanılmayan bölgeleri birleştirerek ve bunları işletim sistemine yeniden bırakarak yığındaki boş bellek miktarını en aza indirir. İşletim sisteminde yayımlanmayan serbest bırakılan bellek, ücretsiz havuza geri yüklenir ve yeniden tahsis için kullanılabilir.

**_Freea** çağrısı, **_malloca**'ya yapılan tüm çağrılara eşlik etmelidir. Aynı bellekte **_freea** 'yi iki kez çağırmak da bir hatadır. Uygulama C çalışma zamanı kitaplıklarının hata ayıklama sürümü ile bağlantılı olduğunda, özellikle **_Crtdbg_map_ayırma**tanımlayarak etkinleştirilen [_malloc_dbg](malloc-dbg.md) özellikleri ile, **_freea**'ya yönelik eksik veya yinelenen çağrıları bulmak daha kolay olur. Hata ayıklama işlemi sırasında yığının nasıl yönetildiği hakkında daha fazla bilgi için bkz. [CRT hata ayıklama yığını](/visualstudio/debugger/crt-debug-heap-details).

**_freea** işaretlenir `__declspec(noalias)`, yani işlevin genel değişkenleri değiştirmeyeceği garanti edilir. Daha fazla bilgi için bkz. [noalias](../../cpp/noalias.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_freea**|\<Stdlib. h > ve \<malloc. h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

[_Malloca](malloca.md)örneğine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Bellek Ayırma](../../c-runtime-library/memory-allocation.md)<br/>
[_malloca](malloca.md)<br/>
[calloc](calloc.md)<br/>
[malloc](malloc.md)<br/>
[_malloc_dbg](malloc-dbg.md)<br/>
[realloc](realloc.md)<br/>
[_free_dbg](free-dbg.md)<br/>
[_heapmin](heapmin.md)<br/>
