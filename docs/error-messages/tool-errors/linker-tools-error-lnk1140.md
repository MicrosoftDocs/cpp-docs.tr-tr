---
title: Bağlayıcı araçları hatası LNK1140 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1140
dev_langs:
- C++
helpviewer_keywords:
- LNK1140
ms.assetid: 468d7651-a7cd-47b9-aead-5bb2fab56121
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9f850360bc749a41e548cebae9f58f9fc7d3d420
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46044710"
---
# <a name="linker-tools-error-lnk1140"></a>Bağlayıcı Araçları Hatası LNK1140

program veritabanı için çok fazla modül; bağlantı/pdb: NONE

Proje, en fazla 4096 modüller içerir.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>Aşağıdaki olası çözümleri kullanarak düzeltmek için

1. Kullanarak yeniden Bağla [/pdb: NONE](../../build/reference/pdb-use-program-database.md).

1. Bazı modüller, hata ayıklama bilgileri olmadan derleyin.

1. Modüller sayısını azaltın.