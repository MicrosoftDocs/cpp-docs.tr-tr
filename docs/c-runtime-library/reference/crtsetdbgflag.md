---
title: _CrtSetDbgFlag
ms.date: 11/04/2016
apiname:
- _CrtSetDbgFlag
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
- _CRTDBG_REPORT_FLAG
- _CRTDBG_CHECK_EVERY_16_DF
- _CRTDBG_CHECK_DEFAULT_DF
- CRTDBG_CHECK_DEFAULT_DF
- CRTDBG_CHECK_EVERY_128_DF
- CRTDBG_CHECK_EVERY_1024_DF
- _CRTDBG_CHECK_EVERY_128_DF
- CrtSetDbgFlag
- CRTDBG_CHECK_EVERY_16_DF
- _CRTDBG_CHECK_EVERY_1024_DF
- _CrtSetDbgFlag
- CRTDBG_REPORT_FLAG
helpviewer_keywords:
- _CRTDBG_CHECK_EVERY_16_DF macro
- CRTDBG_CHECK_EVERY_16_DF macro
- _CRTDBG_CHECK_ALWAYS_DF macro
- _CRTDBG_CHECK_DEFAULT_DF macro
- CRTDBG_ALLOC_MEM_DF macro
- CRTDBG_CHECK_ALWAYS_DF macro
- _CRTDBG_ALLOC_MEM_DF macro
- _CRTDBG_REPORT_FLAG macro
- _CRTDBG_CHECK_EVERY_128_DF macro
- CRTDBG_REPORT_FLAG macro
- _CRTDBG_CHECK_EVERY_1024_DF macro
- CRTDBG_CHECK_DEFAULT_DF macro
- CRTDBG_CHECK_EVERY_1024_DF macro
- _CrtSetDbgFlag function
- CrtSetDbgFlag function
- _CRTDBG_DELAY_FREE_MEM_DF macro
- CRTDBG_CHECK_EVERY_128_DF macro
- CRTDBG_DELAY_FREE_MEM_DF macro
- CRTDBG_CHECK_CRT_DF macro
- _CRTDBG_CHECK_CRT_DF macro
ms.assetid: b5657ffb-6178-4cbf-9886-1af904ede94c
ms.openlocfilehash: 1113854f1b41081ddcf59444786109fb5eabc65d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50621097"
---
# <a name="crtsetdbgflag"></a>_CrtSetDbgFlag

Alır ya da durumunu değiştirir **_crtDbgFlag** hata ayıklama yığını Yöneticisi (yalnızca hata ayıklama sürümü) ayırma davranışını denetleyen bayrak.

## <a name="syntax"></a>Sözdizimi

```C
int _CrtSetDbgFlag(
   int newFlag
);
```

### <a name="parameters"></a>Parametreler

*YeniBayrak*<br/>
Yeni durumu **_crtDbgFlag**.

## <a name="return-value"></a>Dönüş Değeri

Önceki durumunu döndürür **_crtDbgFlag**.

## <a name="remarks"></a>Açıklamalar

**_CrtSetDbgFlag** işlevine izin verir, bit alanları değiştirerek hata ayıklama yığını Yöneticisi bellek ayırmaları nasıl izlediği denetlemek uygulamanın **_crtDbgFlag** bayrağı. Uygulama çıkış yaptığında bellek sızıntıları için denetleme ve herhangi bir güncelleştirme varsa, raporlama dahil olmak üzere, özel hata ayıklama işlemleri gerçekleştirmek için hata ayıklama yığını Yöneticisi (açma) BITS olan, uygulama bildirebilirsiniz ayarıyla tarafından düşük bellek koşulları benzetimi bırakılmış bellek blokları yığının bağlantılı listesinde kalması gerektiğini belirten ve her bellek bloğu her ayırma isteği inceleyerek yığının bütünlüğünü doğrulanıyor. Zaman [_DEBUG](../../c-runtime-library/debug.md) tanımlı değil, çağrılar **_CrtSetDbgFlag** ön işleme sırasında kaldırılır.

Bit alanları aşağıdaki tabloda **_crtDbgFlag** ve davranışları açıklanmaktadır. BITS sonuçları artan tanılama çıktıları ve azaltılmış programı yürütme hızını ayarlamak için bu bitler (varsayılan olarak kapalı) ayarlanmadı. Bunlar hakkında daha fazla bilgi için bit alanları, bkz: [yığın durumu raporlama işlevleri](/visualstudio/debugger/crt-debug-heap-details).

|Bit alanı|Varsayılan|Açıklama|
|---------------|-------------|-----------------|
|**_CRTDBG_ALLOC_MEM_DF**|AÇIK|Açık: hata ayıklama yığın ayırma ve kullanımı, bellek bloğu türü tanıtıcıları, gibi etkinleştirme **_clıent_block**. Kapalı: öbeğinin bağlantılı listesinde yeni ayırmaları eklemek, ancak ayarlanmış engelleme türü **_ıgnore_block**.<br /><br /> Ayrıca herhangi bir yığın sıklığı onay makroları ile birleştirilebilir.|
|**_CRTDBG_CHECK_ALWAYS_DF**|KAPALI|Açık: Çağrı [_CrtCheckMemory](crtcheckmemory.md) her ayırmayı ve ayırmayı kaldırma isteği. Kapalı: **_CrtCheckMemory** özel olarak çağrılması gerekir.<br /><br /> Bu bayrak ayarlandığında yığın sıklığı onay makroları bir etkisi yoktur.|
|**_CRTDBG_CHECK_CRT_DF**|KAPALI|Açık: Dahil **_CRT_BLOCK** sızıntı algılama ve bellek durumu türlerinde fark operations. Kapalı: çalışma zamanı kitaplığı tarafından dahili olarak kullanılan bellek bu işlemleri tarafından göz ardı edilir.<br /><br /> Ayrıca herhangi bir yığın sıklığı onay makroları ile birleştirilebilir.|
|**_CRTDBG_DELAY_FREE_MEM_DF**|KAPALI|Açık: Keep yığın bloklarında bağlantılı liste bellek serbest, bunları atayabilir **_FREE_BLOCK** yazın ve bunları 0xDD bir bayt değeriyle doldurun. Kapalı: bırakılmış blokları yığının bağlantılı listesinde tutma.<br /><br /> Ayrıca herhangi bir yığın sıklığı onay makroları ile birleştirilebilir.|
|**_CRTDBG_LEAK_CHECK_DF**|KAPALI|Açık: otomatik sızıntı bir çağrı aracılığıyla program çıkışında denetimi gerçekleştirmek [_CrtDumpMemoryLeaks](crtdumpmemoryleaks.md) ve uygulama, ayırdığı tüm belleği boşaltmak başarısız olduysa bir hata raporu oluşturun. Kapalı: otomatik olarak denetleme program çıkışında sızıntı gerçekleştirmeyin.<br /><br /> Ayrıca herhangi bir yığın sıklığı onay makroları ile birleştirilebilir.|

**Yığın denetim sıklığı makroları**

C çalışma zamanı kitaplığı hata ayıklama yığın doğrulama ne sıklıkta gerçekleştirir belirtebilirsiniz (**_CrtCheckMemory**) yapılan çağrıların göre **malloc**, **realloc**, **ücretsiz**, ve **_msize**.

**_CrtSetDbgFlag** ardından üst 16 bit inceler *YeniBayrak* parametresi için bir değer. Belirtilen değer sayısıdır **malloc**, **realloc**, **ücretsiz**, ve **_msize** arasında çağırır **_CrtCheckMemory**  çağırır. Dört önceden tanımlanmış makrolar, bu amaç için sağlanır.

|Makrosu|Malloc ve boş realloc _msize çağrılarını _CrtCheckMemory yapılan çağrılar arasında|
|-----------|------------------------------------------------------------------------------------------|
|_CRTDBG_CHECK_EVERY_16_DF|16|
|_CRTDBG_CHECK_EVERY_128_DF|128|
|_CRTDBG_CHECK_EVERY_1024_DF|1024|
|_CRTDBG_CHECK_DEFAULT_DF|0 (varsayılan olarak, hiçbir yığın denetim)|

Varsayılan olarak, **_CrtCheckMemory** 1.024 her defa çağırırsınız bir kez çağrılır **malloc**, **realloc**, **ücretsiz**, ve **_ msize**.

Örneğin, bir yığın denetleyin her 16 belirtebilirsiniz **malloc**, **realloc**, **ücretsiz**, ve **_msize** aşağıdaki kod ile işlemleri:

```C
#include <crtdbg.h>
int main( )
{
    int tmp;

    // Get the current bits
    tmp = _CrtSetDbgFlag(_CRTDBG_REPORT_FLAG);

    // Clear the upper 16 bits and OR in the desired freqency
    tmp = (tmp & 0x0000FFFF) | _CRTDBG_CHECK_EVERY_16_DF;

    // Set the new bits
    _CrtSetDbgFlag(tmp);
}
```

Üst 16 bit *YeniBayrak* parametre _CRTDBG_CHECK_ALWAYS_DF belirtildiğinde yoksayılır. Bu durumda, **_CrtCheckMemory** her çağırdığında çağırılır **malloc**, **realloc**, **ücretsiz**, ve **_msize**.

*YeniBayrak* uygulamak için yeni durumu **_crtDbgFlag** ve her bit alanları için değerler birleşiminden oluşur.

### <a name="to-change-one-or-more-of-these-bit-fields-and-create-a-new-state-for-the-flag"></a>Bir veya daha fazla bu bit alanları değiştirin ve yeni bir bayrak durumu oluşturmak için

1. Çağrı **_CrtSetDbgFlag** ile *YeniBayrak* eşit **_CRTDBG_REPORT_FLAG** geçerli almak için **_crtDbgFlag** durum ve depolayın geçici bir değişkende döndürülen değer.

1. Tüm bitleri tarafından bit düzeyinde kapatma **veya** (uygulama kodunda bildirim sabitleriyle gösterilir) karşılık gelen bit maskesi ile geçici değişkeni.

1. Diğer bitleri tarafından devre dışı bırakma **ve**- ing bit düzeyinde bir değişkeni **değil** , uygun bir bit maskesi.

1. Çağrı **_CrtSetDbgFlag** ile *YeniBayrak* yeni durumu ayarlamak için geçici değişkende depolanan değere eşit **_crtDbgFlag**.

Aşağıdaki kod, düşük bellekte benzetmekte gösterilmiştir tutarak koşullar bırakılmış bellek blokları yığının bağlantılı listesinde ve engelleme **_CrtCheckMemory** her ayırma isteğiyle çağrılmasını:

```C
// Get the current state of the flag
// and store it in a temporary variable
int tmpFlag = _CrtSetDbgFlag( _CRTDBG_REPORT_FLAG );

// Turn On (OR) - Keep freed memory blocks in the
// heap's linked list and mark them as freed
tmpFlag |= _CRTDBG_DELAY_FREE_MEM_DF;

// Turn Off (AND) - prevent _CrtCheckMemory from
// being called at every allocation request
tmpFlag &= ~_CRTDBG_CHECK_ALWAYS_DF;

// Set the new state for the flag
_CrtSetDbgFlag( tmpFlag );
```

Bellek yönetimi ve hata ayıklama yığınındaki genel bakış için bkz: [CRT hata ayıklama öbeği ayrıntıları](/visualstudio/debugger/crt-debug-heap-details).

Bir bayrağıyla devre dışı bırakmak için **_CrtSetDbgFlag** işlevi, aşağıdakileri yapmalısınız **ve** değişkeni ile bit **değil** bit maskesi.

Varsa *YeniBayrak* geçerli bir değer değil. Bu işlev içinde açıklanan şekilde geçersiz parametre işleyicisi çağırır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütme devam etmesine izin verilirse, bu işlev ayarlar **errno** için **EINVAL** ve önceki durumunu döndürür **_crtDbgFlag**.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_CrtSetDbgFlag**|\<crtdbg.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Hata ayıklama sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md) yalnızca.

## <a name="example"></a>Örnek

```C
// crt_crtsetdflag.c
// compile with: /c -D_DEBUG /MTd -Od -Zi -W3 /link -verbose:lib /debug

// This program concentrates on allocating and freeing memory
// blocks to test the functionality of the _crtDbgFlag flag.

#include <string.h>
#include <malloc.h>
#include <crtdbg.h>

int main( )
{
    char *p1, *p2;
    int tmpDbgFlag;

    _CrtSetReportMode( _CRT_ERROR, _CRTDBG_MODE_FILE );
    _CrtSetReportFile( _CRT_ERROR, _CRTDBG_FILE_STDERR );

    // Set the debug-heap flag to keep freed blocks in the
    // heap's linked list - This will allow us to catch any
    // inadvertent use of freed memory
    tmpDbgFlag = _CrtSetDbgFlag(_CRTDBG_REPORT_FLAG);
    tmpDbgFlag |= _CRTDBG_DELAY_FREE_MEM_DF;
    tmpDbgFlag |= _CRTDBG_LEAK_CHECK_DF;
    _CrtSetDbgFlag(tmpDbgFlag);

    // Allocate 2 memory blocks and store a string in each
    p1 = malloc( 34 );
    p2 = malloc( 38 );
    strcpy_s( p1, 34, "p1 points to a Normal allocation block" );
    strcpy_s( p2, 38, "p2 points to a Client allocation block" );

    // Free both memory blocks
    free( p2 );
    free( p1 );

    // Set the debug-heap flag to no longer keep freed blocks in the
    // heap's linked list and turn on Debug type allocations (CLIENT)
    tmpDbgFlag = _CrtSetDbgFlag(_CRTDBG_REPORT_FLAG);
    tmpDbgFlag |= _CRTDBG_ALLOC_MEM_DF;
    tmpDbgFlag &= ~_CRTDBG_DELAY_FREE_MEM_DF;
    _CrtSetDbgFlag(tmpDbgFlag);

    // Explicitly call _malloc_dbg to obtain the filename and
    // line number of our allocation request and also so we can
    // allocate CLIENT type blocks specifically for tracking
    p1 = _malloc_dbg( 40, _NORMAL_BLOCK, __FILE__, __LINE__ );
    p2 = _malloc_dbg( 40, _CLIENT_BLOCK, __FILE__, __LINE__ );
    strcpy_s( p1, 40, "p1 points to a Normal allocation block" );
    strcpy_s( p2, 40, "p2 points to a Client allocation block" );

    // _free_dbg must be called to free the CLIENT block
    _free_dbg( p2, _CLIENT_BLOCK );
    free( p1 );

    // Allocate p1 again and then exit - this will leave unfreed
    // memory on the heap
    p1 = malloc( 10 );
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Hata Ayıklama Yordamları](../../c-runtime-library/debug-routines.md)<br/>
[_crtDbgFlag](../../c-runtime-library/crtdbgflag.md)<br/>
[_CrtCheckMemory](crtcheckmemory.md)<br/>
