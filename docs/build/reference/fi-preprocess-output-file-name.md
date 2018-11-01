---
title: /Fi (Çıktı Dosyası Adını Önişle)
ms.date: 11/04/2016
f1_keywords:
- /Fi
helpviewer_keywords:
- Fi compiler option (C++)
- -Fi compiler option (C++)
- /Fi compiler option (C++)
- preprocessing output files, file name
ms.assetid: 6d0ba983-a8b7-41ec-84f5-b4688ef8efee
ms.openlocfilehash: d4de722ad33a9c9e5e7c37176bbe5d7031b68a39
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50450186"
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
[/P (Dosyaya Önişle)](../../build/reference/p-preprocess-to-a-file.md)<br/>
[Yol Adını Belirtme](../../build/reference/specifying-the-pathname.md)