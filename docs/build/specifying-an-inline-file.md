---
title: Satır içi dosya belirtme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, inline files
- inline files [C++], specifying NMAKE
- files [C++], inline
ms.assetid: 393eccfb-3fc9-4bac-a30c-8ac8d221cca3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2c0d85436aef5ed48c0a8787f8bce330bf6d3e96
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="specifying-an-inline-file"></a>Satır İçi Dosya Belirtme
İki köşeli belirtin (<<) komutta nerede *filename* görünecektir. Köşeli makrosu genişletme olamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<<[filename]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Komutu çalıştırdığınızda, köşeli parantez değiştirilir *filename*, belirtildiği takdirde veya NMAKE oluşturulan benzersiz bir ad. Belirtilmişse, *filename* köşeli bir boşluk veya sekme olmadan izlemeniz gerekir. Bir yola izin verilir. Hiçbir uzantı gerekli veya olduğu varsayılır. Varsa *filename* belirtilirse, dosyanın geçerli oluşturulur veya belirtilen dizin, var olan üzerine dosya bu adı; Aksi takdirde TMP dizininde oluşturulur (veya geçerli dizinin varsa TMP ortam değişkeni tanımlı değil). Bir önceki varsa *filename* olduğundan yeniden, NMAKE önceki dosya ile değiştirir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleme Görevleri Dosyasındaki Satır İçi Dosyalar](../build/inline-files-in-a-makefile.md)