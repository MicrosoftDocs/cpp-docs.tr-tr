---
title: LINK komut dosyaları | Microsoft Docs
ms.custom: ''
ms.date: 09/05/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- link
dev_langs:
- C++
helpviewer_keywords:
- syntax, LINK command files
- command files [C++]
- LINK tool [C++]
- text files, passing arguments to LINK
- LINK tool [C++], command-line syntax
- command files [C++], LINK
ms.assetid: 7154511c-32b9-4e5b-a515-3922fa9de48e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8934758d8aa406ea7b7c959b1fc535cde32195b1
ms.sourcegitcommit: d10a2382832373b900b1780e1190ab104175397f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/06/2018
ms.locfileid: "43894687"
---
# <a name="link-command-files"></a>LINK Komut Dosyaları

Komut satırı bağımsız değişkenleri, bir komut dosyası biçiminde bağlantıya geçirebilirsiniz. Bağlayıcı için bir komut dosyası belirtmek için aşağıdaki sözdizimini kullanın:

> **Bağlantı \@**  <em>commandfile</em>

*Commandfile* bir metin dosyasının adıdır. Hiçbir boşluk veya sekme arasında izin at işareti (**\@**) ve dosya adı. Hiçbir varsayılan uzantı yoktur; herhangi bir uzantısına dahil olmak üzere tam dosya adı belirtmeniz gerekir. Joker karakterler kullanılamaz. Mutlak veya göreli bir yol ile dosya adını belirtebilirsiniz. BAĞLANTI, dosyayı aramak için bir ortam değişkeni kullanmaz.

Komut dosyasında bağımsız değişkenleri tarafından boşluk veya sekme (komut satırında gibi) ayrılabilir ve yeni satır karakterleri.

Komut satırının bir kısmını veya tamamını bir komut dosyasında belirtebilirsiniz. Birden fazla komut dosyasında bir LINK komutunu kullanabilirsiniz. Komut satırında o konumda belirtildi alacağı bağlantı komut dosyası girişi kabul eder. Komut dosyaları iç içe olamaz. BAĞLANTI yankılayan komut dosyalarının içeriğini sürece [/nologo](../../build/reference/nologo-suppress-startup-banner-linker.md) seçeneği belirtildi.

## <a name="example"></a>Örnek

Bir DLL yapılandırmak için aşağıdaki komutu ayrı komut dosyaları nesne dosyaları ve kitaplıkları adlarını geçirir ve kullanır, dosya/EXPORTS seçeneğinin belirtimi için üçüncü komut:

```cmd
link /dll @objlist.txt @liblist.txt @exports.txt
```

## <a name="see-also"></a>Ayrıca Bkz.

[Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)