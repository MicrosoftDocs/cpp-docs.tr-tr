---
title: Bağlayıcı Araçları Hatası LNK1140
ms.date: 11/04/2016
f1_keywords:
- LNK1140
helpviewer_keywords:
- LNK1140
ms.assetid: 468d7651-a7cd-47b9-aead-5bb2fab56121
ms.openlocfilehash: 48c735f29918c4d1caeb15123f7376276d116fb4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62255072"
---
# <a name="linker-tools-error-lnk1140"></a>Bağlayıcı Araçları Hatası LNK1140

program veritabanı için çok fazla modül; bağlantı/pdb: NONE

Proje, en fazla 4096 modüller içerir.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>Aşağıdaki olası çözümleri kullanarak düzeltmek için

1. Kullanarak yeniden Bağla [/pdb: NONE](../../build/reference/pdb-use-program-database.md).

1. Bazı modüller, hata ayıklama bilgileri olmadan derleyin.

1. Modüller sayısını azaltın.