---
title: Komut Satırı Uyarısı D9027
ms.date: 11/04/2016
f1_keywords:
- D9027
helpviewer_keywords:
- D9027
ms.assetid: 2a29edc5-5649-48f2-9058-2057c747284c
ms.openlocfilehash: f89e7416efe7a0069ee2dae8df921933bbe76bcf
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50482608"
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