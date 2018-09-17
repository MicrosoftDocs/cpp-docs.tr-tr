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
ms.openlocfilehash: 3ffe9a440396df14823775db335e52bca6cacdb3
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45725029"
---
# <a name="order-of-cl-options"></a>CL Seçenekleri Sırası

Seçenekleri, CL komut satırında son gerçekleşmelidir/Link seçeneği dışında herhangi bir yerde görünebilir. Belirtilen seçeneklerle derleyici başlar [CL ortam değişkeninde](../../build/reference/cl-environment-variables.md) ve komut satırı soldan sağa okur; bunları bulduğu sırada komut dosyaları işleme. Her seçeneğin komut satırında tüm dosyalar için geçerlidir. CL çakışan seçenekler karşılaşırsa, en sağdaki seçeneğini kullanır.

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici Komut Satırı Sözdizimi](../../build/reference/compiler-command-line-syntax.md)