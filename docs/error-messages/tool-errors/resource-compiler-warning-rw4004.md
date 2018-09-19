---
title: Kaynak Derleyicisi uyarısı RW4004 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- RW4004
dev_langs:
- C++
helpviewer_keywords:
- RW4004
ms.assetid: 596b6a89-9ce7-4ba7-bdcb-e8054c7efafa
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 33305f1f86c0cc1722e4a235ec27927f6e70675f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46095995"
---
# <a name="resource-compiler-warning-rw4004"></a>Kaynak Derleyicisi Uyarısı RW4004

ASCII karakter için sanal anahtar kodu eşdeğer değil

Bir dize sabit değeri, sanal anahtar VIRTKEY'e Türü Hızlandırıcı kodunu kullanıldı.

Bu uyarı, devam etmek, ancak oluşturulan kısayol tuşları belirttiğiniz dizesi eşleşmeyebilir unutmayın olanak tanır. (VIRTKEYs ASCII Hızlandırıcıları değerinden farklı anahtar kodlarını kullanın.)

Dize değişmez değerleri sözdizimsel açıdan geçerli olsa da, yalnızca istediğiniz kullanarak Hızlandırıcı alma sağlayabilirsiniz **VK_\* #define** WINDOWS.h değerleri.