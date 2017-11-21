---
title: _CrtSetDbgFlag | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _CrtSetDbgFlag
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
dev_langs: C++
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
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 5a159deb22b903351c989ca3e8ec43ab7843dd3c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="crtsetdbgflag"></a>_CrtSetDbgFlag
Alır ya da durumunu değiştirir **_crtDbgFlag** hata ayıklama yığını Yöneticisi'ni (yalnızca hata ayıklama sürümü) ayırma davranışını denetlemek için bayrak.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      int _CrtSetDbgFlag(   
   int newFlag   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `newFlag`  
 İçin yeni durum **_crtDbgFlag**.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Önceki durumunu döndürür **_crtDbgFlag**.  
  
## <a name="remarks"></a>Açıklamalar  
 `_CrtSetDbgFlag` İşlevi sağlayan nasıl bit alanlarını değiştirerek hata ayıklama yığını Yöneticisi bellek ayırmaları izler denetlemek uygulama **_crtDbgFlag** bayrağı. Düşük bellek koşullarına göre uygulama çıktığında bellek sızıntıları için denetleme ve herhangi bir varsa bulunan, raporlama dahil olmak üzere özel hata ayıklama işlemleri gerçekleştirmek için hata ayıklama yığını Yöneticisi'ni (açma) BITS olan, uygulama söyleyebilirsiniz ayarıyla benzetimini yapma boşaltılmış bellek blokları öbek 's bağlantılı listesinde kalması gerektiğini belirtme ve her bellek bloğu her ayırma isteği inceleyerek öbek bütünlüğünü doğrulama. Zaman [_DEBUG](../../c-runtime-library/debug.md) tanımlı değil, çağrılar `_CrtSetDbgFlag` ön işleme sırasında kaldırılır.  
  
 Bit alanları için aşağıdaki tabloda listelenmektedir **_crtDbgFlag** ve davranışları açıklanmaktadır. BITS sonuçları artan tanılama çıktıları ve azaltılmış program yürütme hızını ayarlamak için bu bitler (varsayılan olarak kapalı) ayarlanmadı. Bunlar hakkında daha fazla bilgi için alanları bit, bkz: [yığın durumu raporlama işlevleri](/visualstudio/debugger/crt-debug-heap-details).  
  
|Bit alan|Varsayılan|Açıklama|  
|---------------|-------------|-----------------|  
|**_CRTDBG_ALLOC_MEM_DF**|AÇIK|ON: hata ayıklama öbek ayırma ve kullanımı Bellek Blok türü tanımlayıcıların gibi etkinleştirmek `_CLIENT_BLOCK`. Kapalı: yeni ayırmaları yığın'ın bağlantılı listeye ekleyin, ancak ayarlamak engelleme türüne **_ıgnore_block**.<br /><br /> Ayrıca herhangi bir yığın sıklığı onay makroları ile birleştirilebilir.|  
|**_CRTDBG_CHECK_ALWAYS_DF**|KAPALI|ON: Çağrı [_CrtCheckMemory](../../c-runtime-library/reference/crtcheckmemory.md) her ayırma ve ayırmayı kaldırma isteği. Kapalı: `_CrtCheckMemory` açıkça çağrılmalıdır.<br /><br /> Bu bayrak ayarlandığında yığın sıklığı onay makroları bir etkisi yoktur.|  
|`_CRTDBG_CHECK_CRT_DF`|KAPALI|ON: Dahil `_CRT_BLOCK` türleri algılama ve bellek sızıntısı durumdaki fark işlemleri. Kapalı: dahili olarak çalışma zamanı kitaplığı tarafından kullanılan bellek bu işlemleri tarafından göz ardı edilir.<br /><br /> Ayrıca herhangi bir yığın sıklığı onay makroları ile birleştirilebilir.|  
|**_CRTDBG_DELAY_FREE_MEM_DF**|KAPALI|ON: Koru yığınındaki blokları listesi bağlı belleği serbest, bunları Ata **_FREE_BLOCK** yazın ve 0xDD bayt değeri ile doldurun. Kapalı: Öbek 's bağlantılı listesinde boşaltılmış blokları tutma.<br /><br /> Ayrıca herhangi bir yığın sıklığı onay makroları ile birleştirilebilir.|  
|`_CRTDBG_LEAK_CHECK_DF`|KAPALI|ON: otomatik sızıntısı programdan çıkılırken bir çağrıyla denetimi gerçekleştirmek [_CrtDumpMemoryLeaks](../../c-runtime-library/reference/crtdumpmemoryleaks.md) ve onu ayrılan belleği boşaltmak uygulama başarısız olursa bir hata raporu oluşturun. Kapalı: otomatik olarak program Çıkışta Denetimi sızıntısı gerçekleştirmeyin.<br /><br /> Ayrıca herhangi bir yığın sıklığı onay makroları ile birleştirilebilir.|  
  
 **Yığın onay sıklığını makroları**  
  
 C çalışma zamanı kitaplığı hata ayıklama yığınını doğrulanması ne sıklıkta gerçekleştirir belirtebilirsiniz (`_CrtCheckMemory`) çağrı sayısı temel `malloc`, `realloc`, **ücretsiz**, ve `_msize`.  
  
 `_CrtSetDbgFlag`üst 16 bit inceler `newFlag` parametresi için bir değer. Belirtilen değer sayısıdır `malloc`, `realloc`, **ücretsiz**, ve `_msize` arasında çağırır `_CrtCheckMemory` çağrıları. Dört önceden tanımlı makrolar bu amaç için sağlanır.  
  
|Makrosu|_CrtCheckMemory yapılan çağrılar arasında malloc, realloc, boş ve _msize çağrı sayısı|  
|-----------|------------------------------------------------------------------------------------------|  
|_CRTDBG_CHECK_EVERY_16_DF|16|  
|_CRTDBG_CHECK_EVERY_128_DF|128|  
|_CRTDBG_CHECK_EVERY_1024_DF|1024|  
|_CRTDBG_CHECK_DEFAULT_DF|0 (varsayılan olarak, hiçbir yığın denetim)|  
  
 Varsayılan olarak, `_CrtCheckMemory` her 1.024 kez çağırmanız sonra adlı `malloc`, `realloc`, **ücretsiz**, ve `_msize`.  
  
 Örneğin, bir yığın denetleyin her 16 belirtebilirsiniz `malloc`, `realloc`, **ücretsiz**, ve `_msize` aşağıdaki kodla işlemleri:  
  
```  
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
  
 Üst 16 bit `newFlag` _CRTDBG_CHECK_ALWAYS_DF belirtildiğinde parametresi yok sayılıyor. Bu durumda, `_CrtCheckMemory` her çağırdığında adlı `malloc`, `realloc`, **ücretsiz**, ve `_msize`.  
  
 `newFlag`uygulamak için yeni bir durumda **_crtDbgFlag** ve bit alanların her biri için değerlerin birleşiminden oluşur.  
  
### <a name="to-change-one-or-more-of-these-bit-fields-and-create-a-new-state-for-the-flag"></a>Bir veya daha fazla bu bit alanları değiştirin ve bayrağı için yeni bir durum oluşturmak için  
  
1.  Çağrı `_CrtSetDbgFlag` ile `newFlag` eşit `_CRTDBG_REPORT_FLAG` geçerli almak için **_crtDbgFlag** durum ve döndürülen değer geçici bir değişkende saklayın.  
  
2.  Herhangi bir BITS tarafından Aç `OR`- lık (uygulama kodunda bildirim sabitler tarafından gösterilen) karşılık gelen bit maskesi geçici değişkenle.  
  
3.  Diğer BITS tarafından devre dışı bırakma **ve**- lık bit değişkenle **değil** uygun bit maskesi biri.  
  
4.  Çağrı `_CrtSetDbgFlag` ile `newFlag` için yeni durum ayarlamak için geçici değişkeninde depolanan değerine eşit **_crtDbgFlag**.  
  
 Aşağıdaki kod, düşük bellek benzetimini yapma gösterir keserek koşulları bellek blokları öbek 's bağlantılı listesinde serbest ve engellemek `_CrtCheckMemory` her ayırma isteğiyle çağrılan gelen:  
  
```  
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
  
 Bellek yönetimi ve hata ayıklama yığınını genel bakış için bkz: [CRT hata ayıklama öbeği ayrıntıları](/visualstudio/debugger/crt-debug-heap-details).  
  
 Bir bayrağıyla devre dışı bırakmak için `_CrtSetDbgFlag` işlevi, aşağıdakileri yapmalısınız **ve** bitwise değişkenle **değil** bit maskesi biri.  
  
 Varsa `newFlag` geçerli bir değer değil açıklandığı gibi bu işlevi geçersiz parametre işleyicisi çağırır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Bu işlev devam etmek için yürütülmesine izin veriliyorsa, ayarlar `errno` için `EINVAL` ve önceki durumunu döndürür `_crtDbgFlag`.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_CrtSetDbgFlag`|\<crtdbg.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="libraries"></a>Kitaplıklar  
 Hata ayıklama sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md) yalnızca.  
  
## <a name="example"></a>Örnek  
  
```  
// crt_crtsetdflag.c  
// compile with: /c -D_DEBUG /MTd -Od -Zi -W3 /link -verbose:lib /debug  
/*  
 * This program concentrates on allocating and freeing memory  
 * blocks to test the functionality of the _crtDbgFlag flag..  
 */  
  
#include <string.h>  
#include <malloc.h>  
#include <crtdbg.h>  
  
int main( )  
{  
        char *p1, *p2;  
        int tmpDbgFlag;  
  
        _CrtSetReportMode( _CRT_ERROR, _CRTDBG_MODE_FILE );  
        _CrtSetReportFile( _CRT_ERROR, _CRTDBG_FILE_STDERR );  
        /*  
         * Set the debug-heap flag to keep freed blocks in the  
         * heap's linked list - This will allow us to catch any  
         * inadvertent use of freed memory  
         */  
        tmpDbgFlag = _CrtSetDbgFlag(_CRTDBG_REPORT_FLAG);  
        tmpDbgFlag |= _CRTDBG_DELAY_FREE_MEM_DF;  
        tmpDbgFlag |= _CRTDBG_LEAK_CHECK_DF;  
        _CrtSetDbgFlag(tmpDbgFlag);  
  
        /*  
         * Allocate 2 memory blocks and store a string in each  
         */  
        p1 = malloc( 34 );  
        p2 = malloc( 38 );  
        strcpy_s( p1, 34, "p1 points to a Normal allocation block" );  
        strcpy_s( p2, 38, "p2 points to a Client allocation block" );  
  
        /*  
         * Free both memory blocks  
         */  
        free( p2 );  
        free( p1 );  
  
        /*  
         * Set the debug-heap flag to no longer keep freed blocks in the  
         * heap's linked list and turn on Debug type allocations (CLIENT)  
         */  
        tmpDbgFlag = _CrtSetDbgFlag(_CRTDBG_REPORT_FLAG);  
        tmpDbgFlag |= _CRTDBG_ALLOC_MEM_DF;  
        tmpDbgFlag &= ~_CRTDBG_DELAY_FREE_MEM_DF;  
        _CrtSetDbgFlag(tmpDbgFlag);  
  
        /*  
         * Explicitly call _malloc_dbg to obtain the filename and   
         * line number of our allocation request and also so we can   
         * allocate CLIENT type blocks specifically for tracking  
         */  
        p1 = _malloc_dbg( 40, _NORMAL_BLOCK, __FILE__, __LINE__ );  
        p2 = _malloc_dbg( 40, _CLIENT_BLOCK, __FILE__, __LINE__ );  
        strcpy_s( p1, 40, "p1 points to a Normal allocation block" );  
        strcpy_s( p2, 40, "p2 points to a Client allocation block" );  
  
        /*  
         * _free_dbg must be called to free the CLIENT block  
         */  
        _free_dbg( p2, _CLIENT_BLOCK );  
        free( p1 );  
  
        /*  
         * Allocate p1 again and then exit - this will leave unfreed  
         * memory on the heap  
         */  
        p1 = malloc( 10 );  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata ayıklama yordamları](../../c-runtime-library/debug-routines.md)   
 [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md)   
 [_CrtCheckMemory](../../c-runtime-library/reference/crtcheckmemory.md)