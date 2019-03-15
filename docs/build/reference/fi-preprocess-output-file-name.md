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
ms.openlocfilehash: 990c48a72c3f6017d893ddf9b46bcbb737bfb634
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57820201"
---
# <a name="fi-preprocess-output-file-name"></a>/Fi (Çıktı Dosyası Adını Önişle)

Hangi çıkış dosyasının adını belirtir [/P (dosyaya ön işleme)](p-preprocess-to-a-file.md) derleyici seçeneği önceden işlenmiş çıktı yazar.

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

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[/P (Dosyaya Önişle)](p-preprocess-to-a-file.md)<br/>
[Yol Adını Belirtme](specifying-the-pathname.md)
