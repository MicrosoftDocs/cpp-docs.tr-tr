---
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
ms.openlocfilehash: dd854b6ea19ee08bf1a375a42466ad7abd13b1ee
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50480203"
---
# <a name="order-put-functions-in-order"></a>/ORDER (İşlevleri Sırala)

Ayrı olarak paketlenmiş (COMDAT) işlevleri için bir bağlantı sırası belirtin.

## <a name="syntax"></a>Sözdizimi

> **/ ORDER:\@**<em>dosya adı</em>

### <a name="parameters"></a>Parametreler

*Dosya adı*<br/>
COMDAT işlevleri bağlantı sırası belirten bir metin dosyası.

## <a name="remarks"></a>Açıklamalar

**/Sipariş** derleyici seçeneği, programınızın sayfalama davranışı bir işlevi çağırdığı işlevler birlikte gruplandırarak iyileştirin olanak tanır. Ayrıca sık çağrılan işlevler birlikte gruplayabilirsiniz. Olarak da bilinen bu teknikler, *takas ayarı* veya *disk belleği en iyi duruma getirme*, gereklidir ve disk belleğine gerekmez, çağrılan işlev bellekteki olasılığını artırır.

Bir nesne dosyasına kaynak kodunuzu derlediğinizde, derleyici her işlevi adı verilen kendi bölüme yerleştirme söyleyebilirsiniz bir *COMDAT*, kullanarak [/Gy (işlev düzeyi bağlamayı etkinleştir)](../../build/reference/gy-enable-function-level-linking.md) derleyici seçeneği. **/Sipariş** bağlayıcı seçeneği bağlayıcıya, belirttiğiniz sırada yürütülebilir resmin comdat'ları yerleştirin.

COMDAT sırasını belirlemek için oluşturun bir *yanıt dosyası*, bağlayıcı tarafından yerleştirilecek bunları istediğiniz sırayla satır başına bir ada göre her COMDAT listeleyen bir metin dosyası. Bu dosyanın şu şekilde adını geçirin *filename* parametresinin **/sipariş** seçeneği. C++ işlevleri için işlev adı düzenlenmiş biçiminde COMDAT adıdır. C işlevleri düzenlenmemiş adını kullanmak `main`, ve C++ işlevleri olarak bildirilen `extern "C"`. İşlev adları ve düzenlenmiş adları büyük/küçük harfe duyarlıdır. Düzenlenmiş adlar hakkında daha fazla bilgi için bkz. [düzenlenmiş adlar](../../build/reference/decorated-names.md).

Düzenlenmiş adları, comdat'ları bulmak için kullanın [DUMPBIN](../../build/reference/dumpbin-reference.md) Aracı'nın [/SEMBOLLER](../../build/reference/symbols.md) nesne dosyası seçeneği. Bağlayıcı otomatik olarak bir alt çizgi ekler (**\_**) işlev adı bir soru işareti ile başlayan sürece dosya adlarını yanıt (**?**) veya at işareti ( **\@**). Örneğin, bir kaynak dosyası ise example.cpp, içeren işlevler `int cpp_func(int)`, `extern "C" int c_func(int)` ve `int main(void)`, komut `DUMPBIN /SYMBOLS example.obj` düzenlenmiş adlar listelenir:

```Output
...
088 00000000 SECT1A notype ()    External     | ?cpp_func@@YAHH@Z (int __cdecl cpp_func(int))
089 00000000 SECT22 notype ()    External     | _c_func
08A 00000000 SECT24 notype ()    External     | _main
...
```

Bu durumda, olarak adlarını belirtin `?cpp_func@@YAHH@Z`, `c_func`, ve `main` yanıt dosyanızda.

Birden fazla ise **/sipariş** seçeneği görüntülenir bağlayıcı seçenekleri, belirtilen bir devreye girer.

**/Sipariş** seçeneği artımlı bağlamayı devre dışı bırakır. Bağlayıcı uyarı görebileceğiniz [LNK4075](../../error-messages/tool-errors/linker-tools-warning-lnk4075.md) belirtirseniz bu seçeneği artımlı bağlama etkinse veya belirttiyseniz [/zi (artımlı PDB)](../../build/reference/z7-zi-zi-debug-information-format.md) derleyici seçeneği. Bu uyarı sessiz için kullanabilirsiniz [/Incremental: No](../../build/reference/incremental-link-incrementally.md) artımlı bağlamayı devre dışı bırakın ve kullanmak için bağlayıcı seçeneği [(PDB) oluştur/zi](../../build/reference/z7-zi-zi-debug-information-format.md) derleyici seçeneği artımlı bağlama olmadan bir PDB oluşturulacak.

> [!NOTE]
> Ortak sembol adları statik işlev adlarını değil olduğundan bağlantı statik işlevler düzenlenemiyor. Zaman **/sipariş** belirtildiğinde, bağlayıcı uyarı [LNK4037](../../error-messages/tool-errors/linker-tools-warning-lnk4037.md) bulunamadı ya da statik sipariş yanıt dosyasındaki her bir simge oluşturulur.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **bağlayıcı** > **iyileştirme** özellik sayfası.

1. Değiştirme **işlev sırası** özelliğini yanıt dosyanızın adını içerecek şekilde.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.FunctionOrder%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)