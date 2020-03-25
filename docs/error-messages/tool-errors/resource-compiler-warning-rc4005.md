---
title: Kaynak Derleyicisi Uyarısı RC4005
ms.date: 11/04/2016
f1_keywords:
- RC4005
helpviewer_keywords:
- RC4005
ms.assetid: 71f03b4a-c9a9-415d-920f-bf2e58507f93
ms.openlocfilehash: c428fefa90cceed6a8bc9b7f6e4b95ec2db5e039
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80182415"
---
# <a name="resource-compiler-warning-rc4005"></a>Kaynak Derleyicisi Uyarısı RC4005

' tanımlayıcı ': makro yeniden tanımı

Tanımlayıcı iki kez tanımlanır. Derleyici ikinci makro tanımını kullandı.

Bu uyarı, komut satırında ve bir `#define` yönergesi ile kodda bir makro tanımlayarak oluşabilir. Ayrıca, içerme dosyalarından içeri aktarılan makrolardan kaynaklanabilir.

Uyarıyı ortadan kaldırmak için tanımlardan birini kaldırın veya ikinci tanımdan önce bir `#undef` yönergesi kullanın.
