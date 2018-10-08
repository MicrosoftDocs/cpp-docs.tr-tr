---
title: -EXPORT (bir işlevi dışarı aktarır) | Microsoft Docs
ms.custom: ''
ms.date: 09/05/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.ExportFunctions
- /export
dev_langs:
- C++
helpviewer_keywords:
- /EXPORT linker option
- EXPORT linker option
- -EXPORT linker option
ms.assetid: 0920fb44-a472-4091-a8e6-73051f494ca0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 22b79454b71f4908d71e683d8bebe4611da7cb14
ms.sourcegitcommit: 997e6b7d336cddb388bb6e9e56527725fcaa0624
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/08/2018
ms.locfileid: "48861875"
---
# <a name="export-exports-a-function"></a>/EXPORT (İşlevi Dışarı Aktarır)

Bir işlev adı veya sıra veya veri, programınızı dışarı aktarır.

## <a name="syntax"></a>Sözdizimi

> **/ Dışarı aktarma:**<em>GirişAdı</em>[**,\@**<em>sıralı</em>[**, NONAME**]] [**, veri**]

## <a name="remarks"></a>Açıklamalar

**/Dışarı aktarma** seçeneği programınızı diğer programları işlevi çağırabilir veya verileri dışarı aktarmak için bir işlev veya veri öğesi belirtir. Dışarı aktarmalar, genellikle bir DLL içinde tanımlanır.

*GirişAdı* çağırma program tarafından kullanılacak olan işlev veya veri öğesinin adını aynıdır. *Sıralı* belirtmezseniz, dizin ' % s'aralık 1 ile 65.535; dışarı aktarma tablosuna belirtir *sıralı*, bağlantı bir atar. **NONAME** anahtar sözcüğü işlevin olmadan yalnızca bir sıralı, dışarı bir *GirişAdı*.

**Veri** anahtar sözcüğü, dışarı aktarılan öğesi bir veri öğesi olduğunu belirtir. Veri öğesi istemci programı kullanılarak bildirilmelidir **extern __declspec(dllimport)**.

Önerilen Kullanım sırasına göre listelenmiş bir tanımını dışarı aktarma için dört yöntemleri vardır:

1. [__declspec(dllexport)](../../cpp/dllexport-dllimport.md) kaynak kodunda

1. Bir [dışarı AKTARMALARI](../../build/reference/exports.md) .def dosyası deyimi

1. Bir LINK komutunu/Export belirtiminde

1. A [yorum](../../preprocessor/comment-c-cpp.md) yönergesi, kaynak kodda, formun `#pragma comment(linker, "/export: definition ")`.

Bu yöntemlerin tümü, aynı programda kullanılabilir. BAĞLANTI dışarı aktarmaları içeren bir program oluşturduğunda, yapı .exp dosyasının kullanılmadığı sürece ayrıca bir içeri aktarma kitaplığı oluşturur.

BAĞLANTI kullanan tanımlayıcıların forms düzenlenmiş. .Obj dosyası oluşturduğunda, derleyici tanımlayıcı düzenler. Varsa *GirişAdı* bağlayıcıda ve onun için belirttiğiniz (kaynak kodunda göründüğü gibi) oluşturmak, bağlantı denemeleri adıyla eşleşecek şekilde. Benzersiz bir eşleşme bulamazsa, bağlantı bir hata iletisi verir. Kullanım [DUMPBIN](../../build/reference/dumpbin-reference.md) almak için aracı [ile düzenlenmiş adın](../../build/reference/decorated-names.md) bağlayıcıya belirtmek gerektiğinde bir tanımlayıcının formu.

> [!NOTE]
> C tanımlayıcıları, bildirilen düzenlenmiş biçiminde belirtmeyin `__cdecl` veya `__stdcall`.

Bir ve işlev adı dışarı aktarma ve derleme yapılandırmasına bağlı olarak farklı verir (örneğin, 32 bit veya 64 bit derlemelerde) olması gerekiyorsa, her yapılandırma için farklı DEF dosyaları kullanabilirsiniz. (Koşullu önişlemci yönergeleri DEF dosyaları içinde kullanılamaz.) Alternatif olarak, kullandığınız bir `#pragma comment` işlev bildiriminden önce yönerge burada gösterilen şekilde `PlainFuncName` ve adıdır ve `_PlainFuncName@4` işlev düzenlenmiş adı:

```cpp
#pragma comment(linker, "/export:PlainFuncName=_PlainFuncName@4")
BOOL CALLBACK PlainFuncName( Things * lpParams)
```

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **bağlayıcı** > **komut satırı** özellik sayfası.

1. Seçeneğini girin **ek seçenekler** kutusu.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)
