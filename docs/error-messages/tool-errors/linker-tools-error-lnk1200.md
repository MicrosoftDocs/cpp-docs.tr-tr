---
title: Bağlayıcı araçları hatası LNK1200 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1200
dev_langs:
- C++
helpviewer_keywords:
- LNK1200
ms.assetid: 55771145-915e-4006-ac6c-ac702041eb2f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 03ecd51142bf30230b6b177a36e007345e93bf2c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46059322"
---
# <a name="linker-tools-error-lnk1200"></a>Bağlayıcı Araçları Hatası LNK1200

Program Veritabanı 'filename' okunurken hata oluştu

Program veritabanı (PDB) okunamadı.

Dosya bozulması nedeniyle bu hatayı neden olabilir.

Varsa `filename` PDB olan nesne dosyası kullanarak bir nesne dosyası için derlemeniz [/zi](../../build/reference/z7-zi-zi-debug-information-format.md).

Varsa `filename` ana çıkış dosyası için PDB olduğu ve bir artımlı bağlantı sırasında bu hata oluştu, PDB silip yeniden bağlayın.