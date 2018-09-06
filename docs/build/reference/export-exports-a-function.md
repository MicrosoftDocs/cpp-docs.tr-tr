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
ms.openlocfilehash: 16ec6be15635ebfc085615015b1221231645970d
ms.sourcegitcommit: d10a2382832373b900b1780e1190ab104175397f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/06/2018
ms.locfileid: "43894800"
---
# <a name="export-exports-a-function"></a>/EXPORT (İşlevi Dışarı Aktarır)

Bir işlev adı veya sıra veya veri, programınızı dışarı aktarır.

## <a name="syntax"></a>Sözdizimi

> **/ Dışarı aktarma:**<em>GirişAdı</em>[**,\@**<em>sıralı</em>[**, NONAME**]] [**, veri**]

## <a name="remarks"></a>Açıklamalar

/ Export seçeneğiyle diğer programları işlevi çağırabilirsiniz programınıza ait bir işlev verebilirsiniz. Ayrıca, verileri dışarı aktarabilirsiniz. Dışarı aktarmalar, genellikle bir DLL içinde tanımlanır.

*GirişAdı* çağırma program tarafından kullanılacak olan işlev veya veri öğesinin adını aynıdır. `ordinal` 1 ile 65.535 aralığındaki dışarı aktarma tablosuna bir dizin belirtir; Siz belirtmezseniz `ordinal`, bağlantı bir atar. **NONAME** anahtar sözcüğü işlevin olmadan yalnızca bir sıralı, dışarı bir *GirişAdı*.

**Veri** anahtar sözcüğü, dışarı aktarılan öğesi bir veri öğesi olduğunu belirtir. Veri öğesi istemci programı kullanılarak bildirilmelidir **extern __declspec(dllimport)**.

Önerilen Kullanım sırasına göre listelenmiş bir tanımını dışa aktarmak için üç yöntem vardır:

1. [__declspec(dllexport)](../../cpp/dllexport-dllimport.md) kaynak kodunda

2. Bir [dışarı AKTARMALARI](../../build/reference/exports.md) .def dosyası deyimi

3. Bir LINK komutunu/Export belirtiminde

Her üç yöntemi, aynı programda kullanılabilir. BAĞLANTI dışarı aktarmaları içeren bir program oluşturduğunda, yapı .exp dosyasının kullanılmadığı sürece ayrıca bir içeri aktarma kitaplığı oluşturur.

BAĞLANTI kullanan tanımlayıcıların forms düzenlenmiş. .Obj dosyası oluşturduğunda, derleyici tanımlayıcı düzenler. Varsa *GirişAdı* bağlayıcıda ve onun için belirttiğiniz (kaynak kodunda göründüğü gibi) oluşturmak, bağlantı denemeleri adıyla eşleşecek şekilde. Benzersiz bir eşleşme bulamazsa, bağlantı bir hata iletisi verir. Kullanım [DUMPBIN](../../build/reference/dumpbin-reference.md) almak için aracı [düzenlenmiş adları](../../build/reference/decorated-names.md) bağlayıcıya belirtmek gerektiğinde bir tanımlayıcının formu.

> [!NOTE]
> C tanımlayıcıları, bildirilen düzenlenmiş biçiminde belirtmeyin `__cdecl` veya `__stdcall`.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).

2. Seçin **yapılandırma özellikleri** > **bağlayıcı** > **komut satırı** özellik sayfası.

3. Seçeneğini girin **ek seçenekler** kutusu.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)