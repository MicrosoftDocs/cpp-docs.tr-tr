---
title: _heapwalk | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _heapwalk
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
- api-ms-win-crt-heap-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- heapwalk
- _heapwalk
dev_langs: C++
helpviewer_keywords:
- debugging [CRT], heap-related problems
- heapwalk function
- _heapwalk function
ms.assetid: 2df67649-fb00-4570-a8b1-a4eca5738744
caps.latest.revision: "22"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: caed5b5fec9ff7854905542c093a0d265dee4db5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="heapwalk"></a>_heapwalk
Öbek erişir ve sonraki giriş hakkında bilgi verir.  
  
> [!IMPORTANT]
>  Bu API dışında Windows çalışma zamanı hata ayıklama derlemelerinde yürütün uygulamalarda kullanılamaz. Daha fazla bilgi için bkz: [/ZW ile desteklenmeyen CRT işlevleri](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int _heapwalk(   
   _HEAPINFO *entryinfo   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `entryinfo`  
 Yığın bilgileri içerecek şekilde arabelleği.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `_heapwalk`Malloc.h içinde tanımlanan tamsayı bildirim sabitlerden birini döndürür.  
  
 `_HEAPBADBEGIN`  
 İlk üst bilgileri bulunamadı veya geçersiz.  
  
 `_HEAPBADNODE`  
 Yığın bozulmuş veya hatalı düğüm bulundu.  
  
 `_HEAPBADPTR`  
 `_pentry`alanını `_HEAPINFO` yapısı geçerli bir işaretçi yığına içermiyor veya `entryinfo` null işaretçi.  
  
 `_HEAPEND`  
 Öbek sonuna başarıyla erişildi.  
  
 `_HEAPEMPTY`  
 Yığın başlatılmadı.  
  
 `_HEAPOK`  
 Hiçbir hata kadarki; `entryinfo` sonraki yığın giriş hakkındaki bilgilerle güncelleştirilir.  
  
 Ayrıca, bir hata oluşursa, `_heapwalk` ayarlar `errno` için `ENOSYS`.  
  
## <a name="remarks"></a>Açıklamalar  
 `_heapwalk` İşlevi yığın ile ilgili sorunlar programlarında hata ayıklama yardımcı olur. İşlev çağrısı, her bir giriş çapraz geçiş yapan yığın anlatılmaktadır ve işaretçi türü yapısına döndüren `_HEAPINFO` sonraki yığın girdisi hakkında bilgi içerir. `_HEAPINFO` Malloc.h içinde tanımlanan türü, aşağıdaki öğeleri içerir.  
  
 `int *_pentry`  
 Yığın giriş işaretçi.  
  
 `size_t _size`  
 Yığın giriş boyutu.  
  
 `int _useflag`  
 Yığın giriş kullanılıp kullanılmadığını belirten bayrak.  
  
 Çağrı `_heapwalk` döndüren `_HEAPOK` girişi boyutunu depolayan `_size` alan ve kümelerini `_useflag` ya da alan `_FREEENTRY` veya `_USEDENTRY` (her ikisi de Malloc.h içinde tanımlanan sabittir). Bu öbek ilk giriş hakkında bilgi edinmek için geçirdiğiniz `_heapwalk` gösteren bir işaretçi bir `_HEAPINFO` özelliği yapısı `_pentry` üye `NULL`. İşletim sistemini desteklemiyor, `_heapwalk`işlevi (örneğin, Windows 98), döndürür `_HEAPEND` ve ayarlar `errno` için `ENOSYS`.  
  
 Bu işlev, parametre doğrular. Varsa `entryinfo` null işaretçi açıklandığı gibi geçersiz parametre işleyicisi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa `errno` ayarlanır `EINVAL` ve işlevi döndürür `_HEAPBADPTR`.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|İsteğe bağlı üstbilgi|  
|-------------|---------------------|---------------------|  
|`_heapwalk`|\<malloc.h >|\<errno.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Örnek  
  
```  
// crt_heapwalk.c  
  
// This program "walks" the heap, starting  
// at the beginning (_pentry = NULL). It prints out each  
// heap entry's use, location, and size. It also prints  
// out information about the overall state of the heap as  
// soon as _heapwalk returns a value other than _HEAPOK  
// or if the loop has iterated 100 times.  
  
#include <stdio.h>  
#include <malloc.h>  
  
void heapdump(void);  
  
int main(void)  
{  
    char *buffer;  
  
    heapdump();  
    if((buffer = (char *)malloc(59)) != NULL)  
    {  
        heapdump();  
        free(buffer);  
    }  
    heapdump();  
}  
  
void heapdump(void)  
{  
    _HEAPINFO hinfo;  
    int heapstatus;  
    int numLoops;  
    hinfo._pentry = NULL;  
    numLoops = 0;  
    while((heapstatus = _heapwalk(&hinfo)) == _HEAPOK &&  
          numLoops < 100)  
    {  
        printf("%6s block at %Fp of size %4.4X\n",  
               (hinfo._useflag == _USEDENTRY ? "USED" : "FREE"),  
               hinfo._pentry, hinfo._size);  
        numLoops++;  
    }  
  
    switch(heapstatus)  
    {  
    case _HEAPEMPTY:  
        printf("OK - empty heap\n");  
        break;  
    case _HEAPEND:  
        printf("OK - end of heap\n");  
        break;  
    case _HEAPBADPTR:  
        printf("ERROR - bad pointer to heap\n");  
        break;  
    case _HEAPBADBEGIN:  
        printf("ERROR - bad start of heap\n");  
        break;  
    case _HEAPBADNODE:  
        printf("ERROR - bad node in heap\n");  
        break;  
    }  
}  
```  
  
```Output  
  USED block at 00310650 of size 0100  
  USED block at 00310758 of size 0800  
  USED block at 00310F60 of size 0080  
  FREE block at 00310FF0 of size 0398  
  USED block at 00311390 of size 000D  
  USED block at 003113A8 of size 00B4  
  USED block at 00311468 of size 0034  
  USED block at 003114A8 of size 0039  
...  
  USED block at 00312228 of size 0010  
  USED block at 00312240 of size 1000  
  FREE block at 00313250 of size 1DB0  
OK - end of heap  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bellek ayırma](../../c-runtime-library/memory-allocation.md)   
 [_heapadd](../../c-runtime-library/heapadd.md)   
 [_heapchk](../../c-runtime-library/reference/heapchk.md)   
 [_heapmin](../../c-runtime-library/reference/heapmin.md)   
 [_heapset](../../c-runtime-library/heapset.md)