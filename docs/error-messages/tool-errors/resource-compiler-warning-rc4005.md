---
title: Kaynak Derleyicisi Uyarısı RC4005
ms.date: 11/04/2016
f1_keywords:
- RC4005
helpviewer_keywords:
- RC4005
ms.assetid: 71f03b4a-c9a9-415d-920f-bf2e58507f93
ms.openlocfilehash: 571c4ac285e9477b017dbc21cf9ff733539759d2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50613609"
---
# <a name="resource-compiler-warning-rc4005"></a>Kaynak Derleyicisi Uyarısı RC4005

'identifier': makro yeniden tanımlama

Tanımlayıcı, iki kez tanımlanmış. Derleyici, ikinci bir makro tanımı kullanılır.

Bu uyarı, komut satırında ve kodu ile bir makro tanımlayarak kaynaklanabilir bir `#define` yönergesi. İçerme dosyaları içeri makroları tarafından da kaynaklanabilir.

Uyarıyı ortadan kaldırmak için tanımlardan birini kaldırın veya kullanan bir `#undef` ikinci tanımından önce yönergesi.