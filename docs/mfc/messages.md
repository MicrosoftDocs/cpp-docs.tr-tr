---
title: İletileri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- messages, MFC
- messages [MFC]
ms.assetid: b1476310-a135-42ca-817c-444fb3675491
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f25c9cc70cec598f975bbd242af83597311bdc7c
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46392261"
---
# <a name="messages"></a>İletiler

İleti döngüsü içinde `Run` sınıfının üye işlevinde `CWinApp` alır, çeşitli olayları tarafından oluşturulan iletileri kuyruğa alındı. Örneğin, Kullanıcı fareye tıklayana, Windows farenin sol düğmesine basıldığında WM_LBUTTONDOWN ve farenin sol düğmesi bırakıldığında WM_LBUTTONUP gibi birkaç fare ile ilgili iletiler gönderir. Framework'ün uygulamasını Uygulama ileti döngüsü uygun penceresine ileti gönderir.

İletileri önemli kategorilerini açıklanan [ileti kategorileri](../mfc/message-categories.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Framework'teki İletiler ve Komutlar](../mfc/messages-and-commands-in-the-framework.md)

