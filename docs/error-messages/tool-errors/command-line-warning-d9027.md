---
title: Komut satırı uyarısı D9027 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- D9027
dev_langs:
- C++
helpviewer_keywords:
- D9027
ms.assetid: 2a29edc5-5649-48f2-9058-2057c747284c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 105ebbf62027ac3d9377c513c4f7c59e261b983d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46112531"
---
# <a name="command-line-warning-d9027"></a>Komut Satırı Uyarısı D9027

Kaynak dosya '\<dosya adı >' yoksayıldı

CL.exe giriş kaynağı dosyası yoksayıldı.

Bu uyarı /Fo seçeneği ve /c seçeneği ile bir komut satırında bir çıkış dosyası adı arasında boşluk neden olabilir. Örneğin:

```
cl /c /Fo output.obj input.c
```

/Fo arasında boşluk olmadığından ve `output.obj`, CL.exe alır `output.obj` giriş dosyasının adı. Sorunu gidermek için alanı kaldırın:

```
cl /c /Fooutput.obj input.c
```