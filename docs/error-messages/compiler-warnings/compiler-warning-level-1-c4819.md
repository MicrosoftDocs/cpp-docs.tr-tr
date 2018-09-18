---
title: Derleyici Uyarısı (düzey 1) C4819 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4819
dev_langs:
- C++
helpviewer_keywords:
- C4819
ms.assetid: c0316e85-249c-414d-9df0-622d077c6bc2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ac468bc605c261b66f47fdf40efd1a01a5383d58
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46074285"
---
# <a name="compiler-warning-level-1-c4819"></a>Derleyici Uyarısı (düzey 1) C4819

Dosya (sayı) geçerli kod sayfasında temsil edilemeyen bir karakter içeriyor. Dosya, veri kaybını önlemek için Unicode biçiminde kaydedin.

Bir sistemde, dosyadaki tüm karakterleri temsil edemeyen bir kod ile derlenmiş bir ANSI kaynak dosyası C4819 gerçekleşir.

C4819 gidermek için dosyayı Unicode biçiminde kaydedin. Visual Studio'da **dosya**, **Gelişmiş kaydetme seçenekleri**. İçinde **Gelişmiş kaydetme seçenekleri** iletişim kutusunda, dosyadaki tüm karakterleri temsil edebilen bir kodlama seçin — örneğin, UTF-8 — ve ardından **Tamam**.