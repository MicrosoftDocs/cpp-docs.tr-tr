---
title: -Fi (çıktı dosyası adını Önişle) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /Fi
dev_langs:
- C++
helpviewer_keywords:
- Fi compiler option (C++)
- -Fi compiler option (C++)
- /Fi compiler option (C++)
- preprocessing output files, file name
ms.assetid: 6d0ba983-a8b7-41ec-84f5-b4688ef8efee
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dfe9e54dbafbcbd27763060dc9d81b21bac2503d
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45709409"
---
# <a name="fi-preprocess-output-file-name"></a>/Fi (Çıktı Dosyası Adını Önişle)

Hangi çıkış dosyasının adını belirtir [/P (dosyaya ön işleme)](../../build/reference/p-preprocess-to-a-file.md) derleyici seçeneği önceden işlenmiş çıktı yazar.

## <a name="syntax"></a>Sözdizimi

```
/Fipathname
```

#### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|`pathname`|Tarafından üretilen çıkış dosyasının yolunu ve adını **/P** derleyici seçeneği.|

## <a name="remarks"></a>Açıklamalar

Kullanım **/FI** derleyici seçeneği ile birlikte **/P** derleyici seçeneği.

İçin bir yol belirtirseniz `pathname` parametresi, kaynak dosyanın temel adı önceden işlenmiş çıktı dosyasının temel adı olarak kullanılır. `pathname` Parametre belirli dosya adı uzantısı gerektirmez. Ancak, bir dosya adı uzantısı belirtmezseniz ".i" uzantısı kullanılır.

## <a name="example"></a>Örnek

Aşağıdaki komut satırını PROGRAM.cpp önceden işler, yorumları korur, ekler [#line](../../preprocessor/hash-line-directive-c-cpp.md) yönergeleri ve sonucu MYPROCESS.i dosyaya yazar.

```
CL /P /FiMYPROCESS.I PROGRAM.CPP
```

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici Seçenekleri](../../build/reference/compiler-options.md)<br/>
[/P (dosyaya önişle)](../../build/reference/p-preprocess-to-a-file.md)
[yol adını belirtme](../../build/reference/specifying-the-pathname.md)