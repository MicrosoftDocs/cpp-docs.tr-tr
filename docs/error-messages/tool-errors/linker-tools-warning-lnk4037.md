---
description: 'Daha fazla bilgi edinin: bağlayıcı araçları uyarısı LNK4037'
title: Bağlayıcı Araçları Uyarısı LNK4037
ms.date: 10/04/2017
f1_keywords:
- LNK4037
helpviewer_keywords:
- LNK4037
ms.assetid: 9ba02fd3-b04f-4679-bab9-26fa82cf09bb
ms.openlocfilehash: 78fd5ed9f8e2f82221b64053607846f1b8abc00a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331949"
---
# <a name="linker-tools-warning-lnk4037"></a>Bağlayıcı Araçları Uyarısı LNK4037

>'*symbol*' yok; LIP

Düzenlenmiş ad *sembolü* , programda bulunamadığı için [/Order](../../build/reference/order-put-functions-in-order.md) seçeneği kullanılarak sıralanamıyor. Sıra yanıt dosyasındaki *sembolün* belirtimini denetleyin. Daha fazla bilgi için bkz. [/Order (Işlevleri yerleştirme)](../../build/reference/order-put-functions-in-order.md) bağlayıcı seçeneği.

> [!NOTE]
> Statik işlev adları ortak sembol adları olmadığından, bağlantı statik işlevleri sıralamadığından bağlantı yapılamıyor. **/Order** belirtildiğinde, bu bağlayıcı uyarısı, statik veya bulunmayan sıra yanıt dosyasındaki her bir sembol için oluşturulur.
