---
title: Kaynak Derleyicisi uyarısı RC4005 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- RC4005
dev_langs:
- C++
helpviewer_keywords:
- RC4005
ms.assetid: 71f03b4a-c9a9-415d-920f-bf2e58507f93
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 589fd008b3927887a8144b2fc63d2cbbde2af913
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46028525"
---
# <a name="resource-compiler-warning-rc4005"></a>Kaynak Derleyicisi Uyarısı RC4005

'identifier': makro yeniden tanımlama

Tanımlayıcı, iki kez tanımlanmış. Derleyici, ikinci bir makro tanımı kullanılır.

Bu uyarı, komut satırında ve kodu ile bir makro tanımlayarak kaynaklanabilir bir `#define` yönergesi. İçerme dosyaları içeri makroları tarafından da kaynaklanabilir.

Uyarıyı ortadan kaldırmak için tanımlardan birini kaldırın veya kullanan bir `#undef` ikinci tanımından önce yönergesi.