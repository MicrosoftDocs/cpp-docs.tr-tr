---
title: Bağlayıcı Araçları Uyarısı LNK4037
ms.date: 10/04/2017
f1_keywords:
- LNK4037
helpviewer_keywords:
- LNK4037
ms.assetid: 9ba02fd3-b04f-4679-bab9-26fa82cf09bb
ms.openlocfilehash: 43fae7d0f19f96998d2e1a1739bc3e596bbd9ea9
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80194206"
---
# <a name="linker-tools-warning-lnk4037"></a>Bağlayıcı Araçları Uyarısı LNK4037

>'*symbol*' yok; LIP

Düzenlenmiş ad *sembolü* , programda bulunamadığı için [/Order](../../build/reference/order-put-functions-in-order.md) seçeneği kullanılarak sıralanamıyor. Sıra yanıt dosyasındaki *sembolün* belirtimini denetleyin. Daha fazla bilgi için bkz. [/Order (Işlevleri yerleştirme)](../../build/reference/order-put-functions-in-order.md) bağlayıcı seçeneği.

> [!NOTE]
> Statik işlev adları ortak sembol adları olmadığından, bağlantı statik işlevleri sıralamadığından bağlantı yapılamıyor. **/Order** belirtildiğinde, bu bağlayıcı uyarısı, statik veya bulunmayan sıra yanıt dosyasındaki her bir sembol için oluşturulur.
