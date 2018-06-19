---
title: -ORDER (işlevleri Sırala) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.FunctionOrder
- /order
dev_langs:
- C++
helpviewer_keywords:
- ORDER linker option
- -ORDER linker option
- LINK tool [C++], program optimizing
- /ORDER linker option
- LINK tool [C++], swap tuning
- paging, optimizing
ms.assetid: ecf5eb3e-e404-4e86-9a91-4e5ec157261a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: de9b0fb629a1bf984929ec170f05e25e740e9cd5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32378489"
---
# <a name="order-put-functions-in-order"></a>/ORDER (İşlevleri Sırala)

Ayrı ayrı paketlenmiş (comdat'ı) işlevleri bağlantı sırası belirtin.

## <a name="syntax"></a>Sözdizimi

>/ Sipariş: @*dosya adı*

### <a name="parameters"></a>Parametreler

*Dosya adı*  
Comdat'ı işlevleri bağlantı sırası belirten bir metin dosyası.

## <a name="remarks"></a>Açıklamalar

**/Sipariş** derleyici seçeneği işlevi çağırır işlevleri birlikte gruplayarak programınızın disk belleği davranışı en iyi duruma getirme olanak tanır. Sık kullanılan işlevler birlikte gruplayabilirsiniz. Olarak bilinen bu teknikler *takas ayarı* veya *disk belleği en iyi duruma getirme*, gereklidir ve disk, disk belleğine alınacak yok bellekte çağrılan işlev olan olasılığını artırır.

Bir nesne dosyasına kaynak kodunuzu derlerken her işlev adı verilen kendi bölüme yerleştirilecek derleyici anlayabilirsiniz bir *comdat'ı*, kullanarak [(işlev düzeyi /Gy etkinleştir)](../../build/reference/gy-enable-function-level-linking.md) derleyici seçeneği. **/Sipariş** bağlayıcı seçeneği söyler bağlayıcı belirttiğiniz sırayla yürütülebilir görüntü COMDATs yerleştirin.

Comdat'ı sırayı belirtmek için oluşturma bir *yanıt dosyası*, her comdat'ı her satıra bunları bağlayıcı tarafından yerleştirilmesini istediğiniz sırayla ada göre listeleyen bir metin dosyası. Bu dosyayı olarak adını geçirmek *filename* parametresinin **/sipariş** seçeneği. C++ işlevleri için bir comdat'ı adı işlev adı düzenlenmiş biçimidir. Kullanmak için C işlevlerini ve ad `main`, ve olarak bildirilen C++ işlevler için `extern "C"`. İşlev adları ve düzenlenmiş adları büyük/küçük harfe duyarlıdır. Düzenlenmiş adlar hakkında daha fazla bilgi için bkz: [donatılmış adları](../../build/reference/decorated-names.md). 

COMDATs düzenlenmiş adlarını bulmak için [DUMPBIN](../../build/reference/dumpbin-reference.md) aracın [/SYMBOLS](../../build/reference/symbols.md) nesne dosyası seçeneği. Bağlayıcı otomatik olarak bir alt çizgi başına (\_) işlevine bir soru işaretiyle (?) veya oturum adı başlatana kadar dosya adlarını yanıt (@). Örneğin, bir kaynak dosyası, example.cpp, varsa, işlevleri `int cpp_func(int)`, `extern "C" int c_func(int)` ve `int main(void)`, komut `DUMPBIN /SYMBOLS example.obj` bu düzenlenmiş adlar listeler:

```Output
...
088 00000000 SECT1A notype ()    External     | ?cpp_func@@YAHH@Z (int __cdecl cpp_func(int))
089 00000000 SECT22 notype ()    External     | _c_func
08A 00000000 SECT24 notype ()    External     | _main
...
```

Bu durumda, adları olarak belirtmek `?cpp_func@@YAHH@Z`, `c_func`, ve `main` yanıt dosyası.

Birden fazla ise **/sipariş** görünen bağlayıcı seçeneklerinde seçeneği, belirtilen bir efekt alır.

**/Sipariş** seçeneğini artımlı bağlantılandırma devre dışı bırakır. Uyarı bağlayıcı görebilirsiniz [LNK4075](../../error-messages/tool-errors/linker-tools-warning-lnk4075.md) belirttiğinizde bu seçenek artımlı bağlantılandırma etkinse ya da belirttiğiniz [/zı (artımlı PDB)](../../build/reference/z7-zi-zi-debug-information-format.md) derleyici seçeneği. Bu uyarı sessiz için kullanabileceğiniz [/INCREMENTAL:NO](../../build/reference/incremental-link-incrementally.md) artımlı bağlantılandırma etkinleştirmek ve kullanmak için bağlayıcı seçeneği [/zı (PDB Oluştur)](../../build/reference/z7-zi-zi-debug-information-format.md) artımlı bağlamadan bir PDB oluşturmak için derleyici seçeneği.

> [!NOTE]
> Statik işlev adları değil Ortak sembol adları olduğundan bağlantı statik işlevleri order yapılamıyor. Zaman **/sipariş** belirtilirse, uyarı bağlayıcı [LNK4037](../../error-messages/tool-errors/linker-tools-warning-lnk4037.md) statik veya bulunamadı sipariş yanıt dosyasındaki her simge için oluşturulur.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).  

1. Altında **yapılandırma özellikleri**, açık **bağlayıcı** ve ardından **en iyi duruma getirme** özellik sayfası.

1. Değiştirme **işlevi sipariş** özelliği, yanıt dosyası adını içerir.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.FunctionOrder%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)  
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)