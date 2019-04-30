---
title: Kaynak Derleyicisi Önemli Hatası RC1120
ms.date: 11/04/2016
f1_keywords:
- RC1120
helpviewer_keywords:
- RC1120
ms.assetid: 4e462931-e42e-42e3-8bfc-847677194286
ms.openlocfilehash: eff46ddee118c3355e548c73220b407db0561e36
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62374266"
---
# <a name="resource-compiler-fatal-error-rc1120"></a>Kaynak Derleyicisi Önemli Hatası RC1120

bellek yetersiz bayt sayısı gerekli

Kaynak derleyicisi, depolama, yığında depolayan öğeler için yetersiz. Genellikle bu çok fazla sembol olmasının sonucudur.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>Aşağıdaki olası çözümleri kullanarak düzeltmek için

1. Windows takas dosyası alanı artırın. Takas dosyası alanı artırma hakkında daha fazla bilgi için Windows Yardım sanal bellekte bakın.

1. Gereksiz ekleme dosyaları, özellikle gereksiz `#define`s ve işlev prototipleri.

1. Geçerli dosya iki veya daha fazla dosyalara bölün ve ayrı olarak derleyin.

1. Diğer programları veya önemli miktarda bellek kullanan sistemde çalışan sürücüleri kaldırın.