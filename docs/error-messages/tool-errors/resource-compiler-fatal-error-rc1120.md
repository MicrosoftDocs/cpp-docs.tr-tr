---
title: Kaynak Derleyicisi önemli hatası RC1120 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- RC1120
dev_langs:
- C++
helpviewer_keywords:
- RC1120
ms.assetid: 4e462931-e42e-42e3-8bfc-847677194286
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 62f28e381d4eac0bfd1f010ef3919452635a1b96
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46057008"
---
# <a name="resource-compiler-fatal-error-rc1120"></a>Kaynak Derleyicisi Önemli Hatası RC1120

bellek yetersiz bayt sayısı gerekli

Kaynak derleyicisi, depolama, yığında depolayan öğeler için yetersiz. Genellikle bu çok fazla sembol olmasının sonucudur.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>Aşağıdaki olası çözümleri kullanarak düzeltmek için

1. Windows takas dosyası alanı artırın. Takas dosyası alanı artırma hakkında daha fazla bilgi için Windows Yardım sanal bellekte bakın.

1. Gereksiz ekleme dosyaları, özellikle gereksiz `#define`s ve işlev prototipleri.

1. Geçerli dosya iki veya daha fazla dosyalara bölün ve ayrı olarak derleyin.

1. Diğer programları veya önemli miktarda bellek kullanan sistemde çalışan sürücüleri kaldırın.