---
title: CL seçenekleri sırası | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- cl
dev_langs:
- C++
helpviewer_keywords:
- cl.exe compiler, setting options
ms.assetid: 300908ce-ae00-4b45-964b-e4e69ff6777b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 165e20eefecd20ad9dec9e01b38c5eaa7926e4eb
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="order-of-cl-options"></a>CL Seçenekleri Sırası
Seçenekler CL komut satırında son gerçekleşmelidir/Link seçeneği dışında herhangi bir yerde görünür. Belirtilen seçeneklerle derleyici başlar [CL ortam değişkeni](../../build/reference/cl-environment-variables.md) ve ardından komut satırını soldan sağa okur — bunları bulduğu sırayla komut dosyaları işleme. Her seçenek komut satırında tüm dosyalar için geçerlidir. CL çakışan seçenekleri karşılaşırsa en sağdaki seçeneğini kullanır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Komut Satırı Sözdizimi](../../build/reference/compiler-command-line-syntax.md)