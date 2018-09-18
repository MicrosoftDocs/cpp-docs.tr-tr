---
title: BSCMAKE hatası BK1514 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- BK1514
dev_langs:
- C++
helpviewer_keywords:
- BK1514
ms.assetid: 7c7e2504-a490-44ab-bb1f-47385ee2f4b0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 20f66c5c48547e92aef00568d5488a6293303be1
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46094721"
---
# <a name="bscmake-error-bk1514"></a>BSCMAKE Hatası BK1514

Tüm. SBR dosyaları kesildi, hiç dosya bulunamadı

Bir güncelleştirme için belirtilen .sbr dosyaları hiçbiri özgün gözatma bilgisi (.bsc) dosyası bir parçası olan. Bu hatanın nedeni .sbr dosyaları adlarını bulmak için okuma [BK4502](../../error-messages/tool-errors/bscmake-warning-bk4502.md) önünde uyarıları.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aşağıdaki olası nedenleri kontrol ederek düzeltmek için

1. .SBR veya .bsc için belirtilen yanlış dosya adı.

1. Bozuk .bsc dosyasını BSCMAKE yeniden oluşturmak gereklidir.