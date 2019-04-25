---
title: Bağlayıcı Araçları Hatası LNK1181
ms.date: 08/22/2018
f1_keywords:
- LNK1181
helpviewer_keywords:
- LNK1181
ms.assetid: 984b0db6-e331-4284-b2a7-a212fe96c486
ms.openlocfilehash: 657e78ece2ce4039eb8dc8561abd455c60aaff75
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62254926"
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

## <a name="see-also"></a>Ayrıca bkz.

[/LIBPATH (Ek Libpath)](../../build/reference/libpath-additional-libpath.md)