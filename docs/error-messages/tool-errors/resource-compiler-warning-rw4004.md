---
title: Kaynak Derleyicisi Uyarısı RW4004
ms.date: 11/04/2016
f1_keywords:
- RW4004
helpviewer_keywords:
- RW4004
ms.assetid: 596b6a89-9ce7-4ba7-bdcb-e8054c7efafa
ms.openlocfilehash: ca0fb271a5ab43994ec37cc8d59c33877903f6e8
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80182350"
---
# <a name="resource-compiler-warning-rw4004"></a>Kaynak Derleyicisi Uyarısı RW4004

ASCII karakteri sanal anahtar koduna eşit değil

Bir VIRTKEY türü hızlandırıcısında sanal anahtar kodu için bir dize sabit değeri kullanıldı.

Bu uyarı devam etmenizi sağlar, ancak oluşturulan Hızlandırıcı anahtarlarının belirttiğiniz dizeyle eşleşmeyebilir farkında olabilirsiniz. (VIRTKEYs ASCII hızlandırıcılardan farklı temel kodlar kullanır.)

Dize sabit değerleri sözdizimsel olarak geçerli olsa da, yalnızca WINDOWS. h 'deki **VK_\* #define** değerlerini kullanarak istediğiniz hızlandırıcıyı almanızı sağlayabilirsiniz.
