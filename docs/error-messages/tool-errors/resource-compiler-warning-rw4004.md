---
description: 'Daha fazla bilgi edinin: kaynak derleyicisi uyarısı RW4004'
title: Kaynak Derleyicisi Uyarısı RW4004
ms.date: 11/04/2016
f1_keywords:
- RW4004
helpviewer_keywords:
- RW4004
ms.assetid: 596b6a89-9ce7-4ba7-bdcb-e8054c7efafa
ms.openlocfilehash: 5609d49e242ba7d74025622c53c279ae1b0da854
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97237003"
---
# <a name="resource-compiler-warning-rw4004"></a>Kaynak Derleyicisi Uyarısı RW4004

ASCII karakteri sanal anahtar koduna eşit değil

Bir VIRTKEY türü hızlandırıcısında sanal anahtar kodu için bir dize sabit değeri kullanıldı.

Bu uyarı devam etmenizi sağlar, ancak oluşturulan Hızlandırıcı anahtarlarının belirttiğiniz dizeyle eşleşmeyebilir farkında olabilirsiniz. (VIRTKEYs ASCII hızlandırıcılardan farklı temel kodlar kullanır.)

Dize sabit değerleri sözdizimsel olarak geçerli olsa da, yalnızca WINDOWS. h 'deki **VK_ \* #define** değerlerini kullanarak istediğiniz hızlandırıcıyı almanızı sağlayabilirsiniz.
