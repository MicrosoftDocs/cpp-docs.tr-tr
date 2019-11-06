---
title: Bağlayıcı araçları hatası LNK1120
description: Bağlantıdaki çözümlenmemiş dış sembol hatalarının sayısını raporlayan LNK1120 bağlayıcı hatasını açıklar.
ms.date: 10/31/2019
f1_keywords:
- LNK1120
helpviewer_keywords:
- LNK1120
ms.assetid: 56aa7d36-921f-4daf-b44d-cca0d4fb1b51
ms.openlocfilehash: 21a1ede07a69cdc065dd897715e243115529600d
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/05/2019
ms.locfileid: "73626575"
---
# <a name="linker-tools-error-lnk1120"></a>Bağlayıcı araçları hatası LNK1120

> çözülmemiş dışlar *sayısı*

Error LNK1120, geçerli bağlantıdaki [çözümlenmemiş dış sembol](linker-tools-error-lnk2001.md#what-is-an-unresolved-external-symbol) hatalarının sayısını raporlar.

İlk çözümlenmemiş dış sembol bir [LNK2001](linker-tools-error-lnk2001.md) veya [LNK2019](linker-tools-error-lnk2019.md) hatası tarafından bildirilir. LNK1120 iletisi en son gelir ve çözümlenmemiş sembol hata sayısını gösterir.

> [!IMPORTANT]
> **Bu hatayı çözmeniz gerekmez.** Bu hata, derleme çıkışında LNK2001 ve LNK2019 bağlayıcı hatalarının tümünü düzeltilerek dışarıda olur. İlk bildirilen hatadan başlayarak her zaman sorunları giderin. Daha sonraki hatalara neden olmuş olabilir ve önceki hatalar düzeltildiğinde dışarıda kalabilir.
