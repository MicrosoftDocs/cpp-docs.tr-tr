---
description: Daha fazla bilgi edinin:/ORDER (Işlevleri sırayla yerleştir)
title: /ORDER (İşlevleri Sırala)
ms.date: 09/05/2018
f1_keywords:
- VC.Project.VCLinkerTool.FunctionOrder
- /order
helpviewer_keywords:
- ORDER linker option
- -ORDER linker option
- LINK tool [C++], program optimizing
- /ORDER linker option
- LINK tool [C++], swap tuning
- paging, optimizing
ms.assetid: ecf5eb3e-e404-4e86-9a91-4e5ec157261a
ms.openlocfilehash: 36888cbb24c869d06eaaa5830b95ae76fc42b860
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97226356"
---
# <a name="order-put-functions-in-order"></a>/ORDER (İşlevleri Sırala)

Ayrı paketlenmiş (COMDAT) işlevler için bağlantı sırasını belirtin.

## <a name="syntax"></a>Syntax

> **/Order: \@** <em>dosya adı</em>

### <a name="parameters"></a>Parametreler

*filename*<br/>
COMDAT işlevlerinin bağlantı sırasını belirten bir metin dosyası.

## <a name="remarks"></a>Açıklamalar

**/Order** derleyici seçeneği, çağrı yaptığı işlevlerle birlikte bir işlevi gruplayarak, programınızın sayfalama davranışını iyileştirmenize olanak tanır. Ayrıca, sık sık çağrılan işlevleri de gruplandırabilirsiniz. *Değiştirme ayarlama* veya *sayfalama iyileştirmesi* olarak bilinen bu teknikler, bir çağrılan işlevin gerektiğinde bellek içinde olduğu ve diskten disk belleğine alınamayan bir işlev olasılığını artırır.

Kaynak kodunuzu bir nesne dosyasına derlerken, derleyiciye, [/GY (işlev düzeyi bağlamayı etkinleştir)](gy-enable-function-level-linking.md) derleyici seçeneğini kullanarak her Işlevi *COMDAT* olarak adlandırılan kendi bölümüne koymalarını söyleyebilirsiniz. **/Order** bağlayıcı seçeneği, bağlayıcıya, bu bağlayıcıyı, belirttiğiniz sıraya göre yürütülebilir görüntüye yerleştirmesini söyler.

COMDAT sırasını belirtmek için, her bir COMDAT 'ı ada göre ve bağlayıcı tarafından yerleştirilmesini istediğiniz sırayla listeleyen bir *yanıt dosyası* oluşturun. Bu dosyanın adını **/Order** seçeneğinin *filename* parametresi olarak geçirin. C++ işlevleri için, COMDAT adı işlev adının donatılmış biçimidir. C işlevleri için `main` ve olarak belirtilen C++ işlevleri için, tasarlanmadığı adı kullanın `extern "C"` . İşlev adları ve düzenlenmiş adlar büyük/küçük harfe duyarlıdır. Düzenlenmiş adlar hakkında daha fazla bilgi için bkz. [düzenlenmiş adlar](decorated-names.md).

Comtts 'nizin düzenlenmiş adlarını bulmak için, nesne dosyasında [dumpbin](dumpbin-reference.md) aracının [/Symbols](symbols.md) seçeneğini kullanın. **\_** Ad bir soru işareti (**?**) veya işareti () ile başlıyorsa, bağlayıcı otomatik olarak bir alt çizgi () öğesini yanıt dosyasındaki işlev adlarına ekleyin **\@** . Örneğin, bir kaynak dosyası olan example. cpp, işlevleri içeriyorsa `int cpp_func(int)` `extern "C" int c_func(int)` ve `int main(void)` komut `DUMPBIN /SYMBOLS example.obj` Bu düzenlenmiş adları listeler:

```Output
...
088 00000000 SECT1A notype ()    External     | ?cpp_func@@YAHH@Z (int __cdecl cpp_func(int))
089 00000000 SECT22 notype ()    External     | _c_func
08A 00000000 SECT24 notype ()    External     | _main
...
```

Bu durumda, adları `?cpp_func@@YAHH@Z` , `c_func` , ve olarak `main` yanıt dosyanızda belirtin.

Bağlayıcı seçeneklerinde birden fazla **/Order** seçeneği görünürse, belirtilen son bir seçenek geçerli olur.

**/Order** seçeneği artımlı bağlamayı devre dışı bırakır. Artımlı bağlama etkinse veya [/ZI (artımlı pdb)](z7-zi-zi-debug-information-format.md) derleyici seçeneğini belirlediyseniz bu seçeneği belirttiğinizde bağlayıcı Uyarısı [LNK4075](../../error-messages/tool-errors/linker-tools-warning-lnk4075.md) görebilirsiniz. Bu uyarıyı kapatmak için, artımlı bağlamayı devre dışı bırakmak için [/ıncreıncreoff: No](incremental-link-incrementally.md) bağlayıcı seçeneğini kullanabilir ve artımlı bağlama olmadan bir PDB oluşturmak için [/ZI (pdb oluştur)](z7-zi-zi-debug-information-format.md) derleyici seçeneğini kullanabilirsiniz.

> [!NOTE]
> Statik işlev adları ortak sembol adları olmadığından, bağlantı statik işlevleri sıralamadığından bağlantı yapılamıyor. **/Order** belirtildiğinde, bir statik veya bulunmayan sıra yanıt dosyasındaki her bir sembol için bağlayıcı Uyarısı [LNK4037](../../error-messages/tool-errors/linker-tools-warning-lnk4037.md) oluşturulur.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **bağlayıcı**  >  **iyileştirme** özellik sayfasını seçin.

1. **Işlev sırası** özelliğini, yanıt dosyanızın adını içerecek şekilde değiştirin.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.FunctionOrder%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)
