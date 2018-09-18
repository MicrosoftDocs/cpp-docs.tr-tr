---
title: Kaynak Derleyicisi hatası RC2001 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- RC2001
dev_langs:
- C++
helpviewer_keywords:
- RC2001
ms.assetid: 92bfb4c0-1879-4606-bb9f-ef7368707b4a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d75d0f906ba0d7be75ca5177bc1f58bccd226251
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46039978"
---
# <a name="resource-compiler-error-rc2001"></a>Kaynak Derleyicisi Hatası RC2001

Sabitte

Bir dize sabitine olmadan ya da ikinci satırında bir ters eğik çizgi devam edildi (**\\**) veya kapatma ve açma çift tırnak (**"**).

Kaynak dosyada iki satıra olan bir dize sabitine ayırmak için aşağıdakilerden birini yapın:

- İlk satır satır devamlılığı karakteri olan ters eğik çizgi ile bitmelidir.

- Çift tırnak işareti ile ilk satırdaki dize kapatın ve başka bir tırnak işareti ile dizeyi sonraki satıra açın.

\N, yeni satır karakteri bir dize sabiti ekleme için çıkış dizisi ile ilk satırın sonunda için yeterli değil.