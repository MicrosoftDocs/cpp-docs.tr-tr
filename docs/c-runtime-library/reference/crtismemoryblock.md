---
title: "_Crtısmemoryblock | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _CrtIsMemoryBlock
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
dev_langs: C++
helpviewer_keywords:
- _CrtIsMemoryBlock function
- CrtIsMemoryBlock function
ms.assetid: f7cbbc60-3690-4da0-a07b-68fd7f250273
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ec6bea115ba509c7275a2d220cf4b10c6faecae9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="crtismemoryblock"></a>_CrtIsMemoryBlock
Belirtilen bellek bloğu içinde yerel yığın olduğunu ve bir geçerli hata ayıklama yığını blok türü tanımlayıcısı'nı (yalnızca hata ayıklama sürümü) sahip olduğunu doğrular.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int _CrtIsMemoryBlock(   
   const void *userData,  
   unsigned int size,  
   long *requestNumber,  
   char **filename,  
   int *linenumber   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 [in]`userData`  
 İşaretçi doğrulamak için bellek bloğu başlangıcına.  
  
 [in]`size`  
 Boyutu belirtilen bloğun (bayt cinsinden).  
  
 [out]`requestNumber`  
 İşaretçi blok ayırma sayısına veya `NULL`.  
  
 [out]`filename`  
 İşaretçi blok istenen kaynak dosya adını veya `NULL`.  
  
 [out]`linenumber`  
 Kaynak dosyasında satır numarası işaretçi veya `NULL`.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `_CrtIsMemoryBlock`döndürür `TRUE` belirtilen bellek bloğu yerel yığın içinde bulunur ve geçerli hata ayıklama yığını blok türü tanımlayıcısı; Aksi halde, işlevi döndürür `FALSE`.  
  
## <a name="remarks"></a>Açıklamalar  
 `_CrtIsMemoryBlock` İşlevi, belirtilen bellek bloğu uygulamanın yerel yığın içinde bulunur ve geçerli blok türü tanımlayıcısı sahip olduğunu doğrular. Bu işlev, burada bellek bloğu ayırma başlangıçta istenen nesne ayırma sipariş numarası ve kaynak dosya adı/satır numarasını almak için de kullanılabilir. NULL olmayan değerler geçirmesi `requestNumber`, `filename`, veya `linenumber` parametreleri nedenler `_CrtIsMemoryBlock` blok yerel yığınında bulursa Bellek Blok hata ayıklama üstbilgisi, değerler bu parametreleri ayarlamak için. Zaman [_DEBUG](../../c-runtime-library/debug.md) tanımlı değil, çağrılar `_CrtIsMemoryBlock` ön işleme sırasında kaldırılır.  
  
 Varsa `_CrtIsMemoryBlock` başarısız, döndürdüğü `FALSE` ve çıkış parametreleri varsayılan değerlere başlatılır: `requestNumber` ve `lineNumber` 0 olarak ayarlayın ve `filename` ayarlanır `NULL`.  
  
 Bu işlev döndürdüğünden `TRUE` veya `FALSE`, onu biri olarak geçirilebilir [_ASSERT](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) makroları işleme mekanizması basit bir hata ayıklama hata oluştur. Belirtilen adres yerel yığın içinde bulunduğu değilse, aşağıdaki örnekte bir onaylama işlemi hatasına neden olur:  
  
```  
_ASSERTE( _CrtIsMemoryBlock( userData, size, &requestNumber,   
&filename, &linenumber ) );  
```  
  
 Hakkında daha fazla bilgi için `_CrtIsMemoryBlock` diğer hata ayıklama işlevleri ve makrolar kullanılabilmesi için bkz: [raporlama makroları](/visualstudio/debugger/macros-for-reporting). Nasıl bellek blokları ayrılmış, başlatılmış ve temel yığın hata ayıklama sürümü yönetilen hakkında daha fazla bilgi için bkz: [CRT hata ayıklama öbeği ayrıntıları](/visualstudio/debugger/crt-debug-heap-details).  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_CrtIsMemoryBlock`|\<crtdbg.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="libraries"></a>Kitaplıklar  
 Hata ayıklama sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md) yalnızca.  
  
## <a name="example"></a>Örnek  
 Örneğin bkz [_crtısvalidheappointer](../../c-runtime-library/reference/crtisvalidheappointer.md) konu.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata Ayıklama Yordamları](../../c-runtime-library/debug-routines.md)