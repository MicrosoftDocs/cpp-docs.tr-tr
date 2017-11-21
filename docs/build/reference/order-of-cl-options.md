---
title: "CL seçenekleri sırası | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: cl
dev_langs: C++
helpviewer_keywords: cl.exe compiler, setting options
ms.assetid: 300908ce-ae00-4b45-964b-e4e69ff6777b
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1fdcc4b315f2e223e59e88e2f5876965d106a49c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="order-of-cl-options"></a>CL Seçenekleri Sırası
Seçenekler CL komut satırında son gerçekleşmelidir/Link seçeneği dışında herhangi bir yerde görünür. Belirtilen seçeneklerle derleyici başlar [CL ortam değişkeni](../../build/reference/cl-environment-variables.md) ve ardından komut satırını soldan sağa okur — bunları bulduğu sırayla komut dosyaları işleme. Her seçenek komut satırında tüm dosyalar için geçerlidir. CL çakışan seçenekleri karşılaşırsa en sağdaki seçeneğini kullanır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici komut satırı sözdizimi](../../build/reference/compiler-command-line-syntax.md)