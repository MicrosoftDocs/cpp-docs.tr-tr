---
title: /EXPORT (İşlevi Dışarı Aktarır)
ms.date: 09/05/2018
f1_keywords:
- VC.Project.VCLinkerTool.ExportFunctions
- /export
helpviewer_keywords:
- /EXPORT linker option
- EXPORT linker option
- -EXPORT linker option
ms.assetid: 0920fb44-a472-4091-a8e6-73051f494ca0
ms.openlocfilehash: a55b2a4ce72de644fe426894ab389f62bd29b204
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87232696"
---
# <a name="export-exports-a-function"></a>/EXPORT (İşlevi Dışarı Aktarır)

Bir işlevi, programından ada veya sıraya göre veya verilere göre dışarı aktarır.

## <a name="syntax"></a>Sözdizimi

> **/Export:**<em>EntryName</em>[**, \@ **<em>Ordinal</em>[**, noname**]] [**, veri**]

## <a name="remarks"></a>Açıklamalar

**/Export** seçeneği, programından dışarı aktarılacak bir işlev veya veri öğesi belirtir, böylece diğer programlar işlevi çağırabilir veya verileri kullanabilir. Dışarı aktarmalar genellikle DLL 'de tanımlanmıştır.

*EntryName* , çağıran program tarafından kullanılacak şekilde işlevin veya veri öğesinin adıdır. *Ordinal* , 1 ile 65.535 arasında dışarı aktarmalar tablosuna bir dizin belirtir; *sıra*belirtmezseniz, bağlantı bir tane atar. **Noname** anahtar sözcüğü, *EntryName*olmadan işlevi yalnızca sıra olarak dışa aktarır.

**Data** anahtar sözcüğü, dışarıya aktarılmış öğenin bir veri öğesi olduğunu belirtir. İstemci programındaki veri öğesi **extern __declspec (dllimport)** kullanılarak bildirilmelidir.

Bir tanımı dışarı aktarmak için önerilen kullanım sırasıyla listelenen dört yöntem vardır:

1. kaynak kodunda [__declspec (dllexport)](../../cpp/dllexport-dllimport.md)

1. . Def dosyasındaki [dışarı aktarmalar](exports.md) deyimleri

1. BAĞLANTı komutunda bir/EXPORT belirtimi

1. Formun kaynak kodunda bir [Açıklama](../../preprocessor/comment-c-cpp.md) yönergesi `#pragma comment(linker, "/export: definition ")` .

Tüm bu yöntemler aynı programda kullanılabilir. BAĞLANTı, dışarı aktarmalar içeren bir program oluşturduğunda, derlemede bir. exp dosyası kullanılmadığı takdirde bir içeri aktarma kitaplığı da oluşturur.

BAĞLANTı, düzenlenmiş tanımlayıcıların biçimlerini kullanır. Derleyici,. obj dosyasını oluşturduğunda bir tanımlayıcıyı tasarlaştırır. *EntryName* , yerleşik olmayan biçimde (kaynak kodda göründüğü gibi) bağlayıcıya BELIRTILMIŞSE, bağlantı, adı ile eşleşecek şekilde çalışır. Benzersiz bir eşleşme bulamazsa bağlantı, bir hata iletisi verir. Bir tanımlayıcının kendisini bağlayıcıya belirtmeniz gerektiğinde [düzenlenmiş ad](decorated-names.md) biçimini almak Için [dumpbin](dumpbin-reference.md) aracını kullanın.

> [!NOTE]
> Veya olarak belirtilen C tanımlayıcılarının düzenlenmiş biçimini belirtmeyin **`__cdecl`** **`__stdcall`** .

Numaralandıraktarılmamış bir işlev adını dışa aktarmanız ve derleme yapılandırmasına (örneğin, 32-bit veya 64 bit derlemeler) göre farklı dışarı aktarmalar sahip olmanız gerekiyorsa, her yapılandırma için farklı DEF dosyaları kullanabilirsiniz. (DEF dosyasında Önişlemci koşullu yönergelere izin verilmez.) Alternatif olarak, `#pragma comment` burada gösterildiği gibi bir işlev bildiriminden önce bir yönerge kullanabilirsiniz, burada `PlainFuncName` açıklanmamış ad ve `_PlainFuncName@4` işlevin düzenlenmiş adıdır:

```cpp
#pragma comment(linker, "/export:PlainFuncName=_PlainFuncName@4")
BOOL CALLBACK PlainFuncName( Things * lpParams)
```

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **bağlayıcı**  >  **komut satırı** özellik sayfasını seçin.

1. **Ek seçenekler** kutusuna seçeneği girin.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)
