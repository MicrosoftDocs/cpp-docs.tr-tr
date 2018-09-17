---
title: Yapı içi değerler ve satır içi derleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 8affd4bb-279d-46f3-851f-8be0a9c5ed3f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6a87e577af339099eda56a3b9d91929a05253a43
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45716254"
---
# <a name="intrinsics-and-inline-assembly"></a>Yapı İçi Değerler ve Satır İçi Derleme

Bir x64 için kısıtlamaların derleyici satır içi assembler desteği yok etmektir. İşlevler yani C veya C++ ortamında ya da alt yordamlar veya derleyici tarafından desteklenen iç işlevleri olarak yazılması gerekir yazılamaz. Diğerleri oluşturulmazken belirli performans duyarlı işlevlerdir. Performans açısından duyarlı işlevleri, iç işlev olarak uygulanmalıdır.

Derleyici tarafından desteklenen yapı içlerini açıklanan [derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md).

## <a name="see-also"></a>Ayrıca Bkz.

[x64 Yazılım Kuralları](../build/x64-software-conventions.md)