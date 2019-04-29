---
title: Kaynak Derleyicisi Uyarısı RW4004
ms.date: 11/04/2016
f1_keywords:
- RW4004
helpviewer_keywords:
- RW4004
ms.assetid: 596b6a89-9ce7-4ba7-bdcb-e8054c7efafa
ms.openlocfilehash: bafd1084a665fc656fe184064a48e5fffc61c957
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62346086"
---
# <a name="resource-compiler-warning-rw4004"></a>Kaynak Derleyicisi Uyarısı RW4004

ASCII karakter için sanal anahtar kodu eşdeğer değil

Bir dize sabit değeri, sanal anahtar VIRTKEY'e Türü Hızlandırıcı kodunu kullanıldı.

Bu uyarı, devam etmek, ancak oluşturulan kısayol tuşları belirttiğiniz dizesi eşleşmeyebilir unutmayın olanak tanır. (VIRTKEYs ASCII Hızlandırıcıları değerinden farklı anahtar kodlarını kullanın.)

Dize değişmez değerleri sözdizimsel açıdan geçerli olsa da, yalnızca istediğiniz kullanarak Hızlandırıcı alma sağlayabilirsiniz **VK_\* #define** WINDOWS.h değerleri.