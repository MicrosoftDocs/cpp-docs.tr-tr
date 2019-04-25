---
title: Komut Satırı Uyarısı D9027
ms.date: 11/04/2016
f1_keywords:
- D9027
helpviewer_keywords:
- D9027
ms.assetid: 2a29edc5-5649-48f2-9058-2057c747284c
ms.openlocfilehash: f89e7416efe7a0069ee2dae8df921933bbe76bcf
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62214134"
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