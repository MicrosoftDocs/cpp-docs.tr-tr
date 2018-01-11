---
title: "_Crtısvalidpointer | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _CrtIsValidPointer
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
dev_langs: C++
helpviewer_keywords:
- CrtIsValidPointer function
- _CrtIsValidPointer function
ms.assetid: 91c35590-ea5e-450f-a15d-ad8d62ade1fa
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2a5063a82ca90b9f854adb1ef68328272df54f4c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="crtisvalidpointer"></a>_CrtIsValidPointer
Bir işaretçi null olmadığını doğrular. C çalışma zamanı kitaplığı Visual Studio 2010 önce sürümlerinde, belirtilen bellek aralığı okuma ve yazma (yalnızca hata ayıklama sürümü) için geçerli olduğunu doğrular.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int _CrtIsValidPointer(   
   const void *address,  
   unsigned int size,  
   int access   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 adres  
 Başlangıç noktalarına geçerliliğini sınamak için bellek aralığının.  
  
 `size`  
 Boyutu (bayt cinsinden) belirtilen bellek aralığının.  
  
 erişim  
 Bellek aralığı belirlemek için okuma/yazma erişilebilirlik.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `_CrtIsValidPointer`Belirtilen işaretçisi null değil, TRUE döndürür. Visual Studio 2010 önce CRT kitaplık sürümleri bellek aralığı belirtilen işlem veya işlemleri için geçerli ise TRUE değerini döndürür. Aksi takdirde işlevi FALSE değerini döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 CRT kitaplık Visual Studio 2010 ile başlayarak, boyutu ve erişim parametreleri yok sayılır, ve `_CrtIsValidPointer` yalnızca belirtilen adresi null olmadığını doğrular. Bu test kendiniz gerçekleştirmek kolay olduğundan, bu işlevi kullanmak önerilmez. Visual Studio 2010 önce sürümlerde başlangıç bellek aralığı doğrular işlevi `address` ve için genişletme `size` bayttır belirtilen erişilebilirlik işlemi veya işlemleri için geçerli. Zaman `access` olan TRUE olarak ayarlanırsa, hem okuma ve yazma için bellek aralığı doğrulanır. Zaman `access` false, bellek aralığı yalnızca okuma için doğrulanır. Zaman [_DEBUG](../../c-runtime-library/debug.md) tanımlı değil, çağrılar `_CrtIsValidPointer` ön işleme sırasında kaldırılır.  
  
 Bu işlev TRUE veya false değeri döndürdüğünden, aşağıdakilerden birini geçirilebilir [_ASSERT](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) makroları işleme mekanizması basit bir hata ayıklama hata oluştur. Bellek aralığı hem okuma hem de yazma işlemleri için geçerli değilse, aşağıdaki örnekte bir onaylama işlemi hatasına neden olur:  
  
```  
_ASSERTE( _CrtIsValidPointer( address, size, TRUE ) );  
```  
  
 Hakkında daha fazla bilgi için `_CrtIsValidPointer` diğer hata ayıklama işlevleri ve makrolar kullanılabilmesi için bkz: [raporlama makroları](/visualstudio/debugger/macros-for-reporting). Nasıl bellek blokları ayrılmış, başlatılmış ve temel yığın hata ayıklama sürümü yönetilen hakkında daha fazla bilgi için bkz: [CRT hata ayıklama öbeği ayrıntıları](/visualstudio/debugger/crt-debug-heap-details).  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_CrtIsValidPointer`|\<crtdbg.h >|  
  
 `_CrtIsValidPointer`bir Microsoft uzantısıdır. Uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="libraries"></a>Kitaplıklar  
 Hata ayıklama sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md) yalnızca.  
  
## <a name="example"></a>Örnek  
 Örneğin bkz [_crtısvalidheappointer](../../c-runtime-library/reference/crtisvalidheappointer.md) konu.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata Ayıklama Yordamları](../../c-runtime-library/debug-routines.md)