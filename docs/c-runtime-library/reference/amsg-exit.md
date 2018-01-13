---
title: _amsg_exit | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _amsg_exit
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
f1_keywords: _amsg_exit
dev_langs: C++
helpviewer_keywords: _amsg_exit
ms.assetid: 146d4faf-d763-43a4-b264-12711196456b
caps.latest.revision: "2"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 42981b60a0a3f53c0887fad45bdd41d7ffd2c308
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="amsgexit"></a>_amsg_exit
Belirtilen çalışma zamanı hata iletisi gösterir ve hata kodu 255 uygulamanızla çıkar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
void _amsg_exit (  
   int rterrnum  
   )  
```  
  
#### <a name="parameters"></a>Parametreler  
 `rterrnum`  
 Sistem tarafından tanımlanan çalışma zamanı hata iletisi kimliği sayısı.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlev çalışma zamanı hata iletisine yayar **stderr** konsol uygulamaları veya bir ileti ileti kutusu Windows uygulamaları için görüntüler. Hata ayıklama modunda çıkmadan önce hata ayıklayıcısı çağrılacak seçebilirsiniz.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|_amsg_exit|internal.h|