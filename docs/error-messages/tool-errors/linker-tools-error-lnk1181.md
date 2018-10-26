---
title: Bağlayıcı araçları hatası LNK1181 | Microsoft Docs
ms.custom: ''
ms.date: 08/22/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1181
dev_langs:
- C++
helpviewer_keywords:
- LNK1181
ms.assetid: 984b0db6-e331-4284-b2a7-a212fe96c486
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 787c6c35b698b5dce57c4aaf3acb4eca496ead95
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50072167"
---
# <a name="linker-tools-error-lnk1181"></a>Bağlayıcı Araçları Hatası LNK1181

'filename' giriş dosyası açılamıyor

Bağlayıcı bulunamadı `filename` mevcut olmadığından veya yolu bulunamadı.

Bazı yaygın nedenleri hatası LNK1181 eklemek için:

- `filename` ek bir bağımlılık bağlayıcı satır, ancak dosya yok olarak başvuruluyor.

- A **/Libpath** dizinini içeren ifadesi `filename` eksik.

Yukarıdaki sorunları çözmek için bağlayıcı satırında başvurulan tüm dosyaların sistemde mevcut olduğundan emin olun.  Olduğundan da emin bir **/Libpath** deyimi için bağlı bağlayıcı dosyasını içeren her dizini.

Daha fazla bilgi için [bağlayıcı girişi olarak .lib dosyaları](../../build/reference/dot-lib-files-as-linker-input.md).

Başka bir olası LNK1181 gömülü boşluklarla uzun dosya adları tırnak içine alınmamıştı nedeni.  Bu durumda, bağlayıcı yalnızca ilk alana kadar bir dosya adı tanır ve ardından bir dosya uzantısı varsayılır. obj.  Uzun dosya adı tırnak içine bu duruma yönelik bir çözüm olan (yol ve dosya adı) tırnak işareti içine alınmış.

İle derlerken [/P (dosyaya ön işleme)](../../build/reference/p-preprocess-to-a-file.md) seçeneği, LNK1181 sonuçlanabilir, çünkü bu seçenek .obj dosyaları oluşturulmasını bastırır.

## <a name="see-also"></a>Ayrıca Bkz.

[/LIBPATH (Ek Libpath)](../../build/reference/libpath-additional-libpath.md)