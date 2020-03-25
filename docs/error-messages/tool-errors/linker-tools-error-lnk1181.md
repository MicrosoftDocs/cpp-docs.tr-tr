---
title: Bağlayıcı Araçları Hatası LNK1181
ms.date: 08/22/2018
f1_keywords:
- LNK1181
helpviewer_keywords:
- LNK1181
ms.assetid: 984b0db6-e331-4284-b2a7-a212fe96c486
ms.openlocfilehash: d2b28af52a2ca2263a7bad77c8c69242396ff2b4
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80195259"
---
# <a name="linker-tools-error-lnk1181"></a>Bağlayıcı Araçları Hatası LNK1181

' filename ' giriş dosyası açılamıyor

Bağlayıcı mevcut olmadığından veya yol bulunamadığı için `filename` bulamadı.

Hata LNK1181 için bazı yaygın nedenler şunlardır:

- `filename` bağlayıcı satırına ek bir bağımlılık olarak başvurulur, ancak dosya yok.

- `filename` içeren dizini belirten bir **/LIBPATH** bildirisi yok.

Yukarıdaki sorunları çözmek için bağlayıcı satırında başvurulan tüm dosyaların sistemde bulunduğundan emin olun.  Ayrıca, bağlayıcıya bağlı bir dosya içeren her dizin için bir **/LIBPATH** ifadesinin olduğundan emin olun.

Daha fazla bilgi için, bkz [. lib dosyaları bağlayıcı girişi olarak](../../build/reference/dot-lib-files-as-linker-input.md).

LNK1181 'in bir diğer olası nedeni, katıştırılmış boşluklar içeren uzun bir dosya adının tırnak içine alınmamasına neden olur.  Bu durumda, bağlayıcı yalnızca ilk alana kadar bir dosya adı tanır ve sonra bir. obj dosya uzantısını kabul eder.  Bu durumun çözümü, uzun dosya adını (yol Plus dosya adı) tırnak işaretleri içine almak için kullanılır.

[/P (bir dosyaya Önişle)](../../build/reference/p-preprocess-to-a-file.md) seçeneğiyle derlemek, LNK1181 ile sonuçlanabilir, çünkü bu seçenek. obj dosyalarının oluşturulmasını bastırır.

## <a name="see-also"></a>Ayrıca bkz.

[/LIBPATH (Ek Libpath)](../../build/reference/libpath-additional-libpath.md)
