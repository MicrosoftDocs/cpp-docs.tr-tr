---
title: /MANIFESTUAC (Bildirimdeki UAC bilgilerini katıştırır)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.UACUIAccess
- VC.Project.VCLinkerTool.UACExecutionLevel
- VC.Project.VCLinkerTool.EnableUAC
helpviewer_keywords:
- /MANIFESTUAC linker option
- MANIFESTUAC linker option
- -MANIFESTUAC linker option
ms.assetid: 2d243c39-fa13-493c-b56f-d0d972a1603a
ms.openlocfilehash: 702dae41f873218dab0d3fb24e46dacd710bc20f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50625101"
---
# <a name="manifestuac-embeds-uac-information-in-manifest"></a>/MANIFESTUAC (Bildirimdeki UAC bilgilerini katıştırır)

Kullanıcı Hesabı Denetimi (UAC) bilgisinin program bildiriminde gömülü olup olmadığını belirtir.

## <a name="syntax"></a>Sözdizimi

```
/MANIFESTUAC
/MANIFESTUAC:NO
/MANIFESTUAC:fragment
/MANIFESTUAC:level=_level
/MANIFESTUAC:uiAccess=_uiAccess
```

### <a name="parameters"></a>Parametreler

*Parça*<br/>
İçeren bir dize `level` ve `uiAccess` değerleri. Daha fazla bilgi için bu konunun ilerleyen bölümlerinde Açıklamalar bölümüne bakın.

*_düzeyi*<br/>
Aşağıdakilerden birini *asInvoker*, *highestAvailable*, veya *requireAdministrator'a*. Varsayılan olarak asInvoker. Daha fazla bilgi için bu konunun ilerleyen bölümlerinde Açıklamalar bölümüne bakın.

*_uiAccess*<br/>
**doğru** uygulamanın kullanıcı arabirimi koruma düzeylerinin atlanıp ve sürücü giriş izni yüksek windows masaüstü için; Aksi takdirde istiyorsanız **false**. Varsayılan olarak **false**. Kümesine **true** yalnızca kullanıcı arabirimi erişilebilirlik uygulamaları için.

## <a name="remarks"></a>Açıklamalar

Komut satırında birden çok /MANIFESTUAC seçeneği belirtirseniz, girilen sonuncu önceliklidir.

/MANIFESTUAC:level seçenekleri aşağıdaki gibidir:

- `asInvoker`: Uygulama başlatıldığından işlem olarak aynı izinlere sahip çalışacaktır. Uygulama için daha yüksek bir izin düzeyi seçerek yükseltilebilir **yönetici olarak çalıştır**.

- highestAvailable: uygulama ile alabilir ve en yüksek bir izin düzeyi çalışır. Uygulamayı başlatan kullanıcının Yöneticiler grubunun bir üyesi ise, bu seçenek requireAdministrator'a ile aynıdır. Yüksek kullanılabilir bir izin düzeyi açılışı düzeyinden daha yüksek ise, sistem için kimlik bilgilerini ister.

- requireAdministrator'a: uygulama yönetici izinleriyle çalışacak. Uygulamayı başlatan kullanıcının Yöneticiler grubunun bir üyesi olmalıdır. Açma işlemi yönetim izinleriyle çalışmıyorsa, sistem için kimlik bilgilerini ister.

/MANIFESTUAC:fragment seçeneğini kullanarak tek bir adımda düzeyi ve UIAccess değerleri belirtebilirsiniz. Parça, aşağıdaki biçimde olmalıdır:

```
"level=[ asInvoker | highestAvailable | requireAdministrator ] uiAccess=[ true | false ]"
```

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Genişletin **yapılandırma özellikleri** düğümü.

1. Genişletin **bağlayıcı** düğümü.

1. Seçin **bildirim dosyası** özellik sayfası.

1. Değiştirme **kullanıcı hesabı denetimi (UAC) etkinleştir**, **UAC yürütme düzeyi**, ve **UAC UI korumasını atla** özellikleri.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

1. Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.EnableUAC%2A>, <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.UACExecutionLevel%2A>, ve <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.UACUIAccess%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)