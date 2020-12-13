---
description: Şu konuda daha fazla bilgi edinin:/BILDIRIESTUAC (UAC bilgilerini bildirimde katıştırır)
title: /MANIFESTUAC (Bildirimdeki UAC bilgilerini katıştırır)
ms.date: 06/12/2020
f1_keywords:
- VC.Project.VCLinkerTool.UACUIAccess
- VC.Project.VCLinkerTool.UACExecutionLevel
- VC.Project.VCLinkerTool.EnableUAC
helpviewer_keywords:
- /MANIFESTUAC linker option
- MANIFESTUAC linker option
- -MANIFESTUAC linker option
ms.assetid: 2d243c39-fa13-493c-b56f-d0d972a1603a
ms.openlocfilehash: 165f543dab087ca32c91002811d99b9048fa392b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97137897"
---
# <a name="manifestuac-embeds-uac-information-in-manifest"></a>/MANIFESTUAC (Bildirimdeki UAC bilgilerini katıştırır)

Kullanıcı hesabı denetimi (UAC) bilgisinin program bildirimine katıştırılmadığını belirtir.

## <a name="syntax"></a>Sözdizimi

> **`/MANIFESTUAC`**\
> **`/MANIFESTUAC:NO`**\
> **`/MANIFESTUAC:`**_`level`_\
> **`/MANIFESTUAC:`**_`uiAccess`_\
> **`/MANIFESTUAC:`**_`fragment`_

### <a name="parameters"></a>Parametreler

**`NO`**<br/>
Bağlayıcı, program bildirimine UAC bilgilerini katıştırmaz.

*`level`*<br/>
**`level=`** ardından **`'asInvoker'`** , **`'highestAvailable'`** , veya **`'requireAdministrator'`** . Varsayılan olarak olur **`'asInvoker'`** . Daha fazla bilgi için, [açıklamalar](#remarks) bölümüne bakın.

*`uiAccess`*<br/>
**`uiAccess='true'`** uygulamanın, Kullanıcı arabirimi koruma düzeylerini ve sürücü girişini, masaüstündeki daha yüksek izin üzerine Windows 'a atlaması istiyorsanız; Aksi takdirde, **`uiAccess='false'`** . Varsayılan olarak olur **`uiAccess='false'`** . Bu bağımsız değişkeni **`uiAccess='true'`** yalnızca kullanıcı arabirimi erişilebilirlik uygulamaları için ayarlayın.

*`fragment`*<br/>
Ve değerlerini içeren bir dize *`level`* *`uiAccess`* . İsteğe bağlı olarak çift tırnak içine alınmış olabilir. Daha fazla bilgi için, [açıklamalar](#remarks) bölümüne bakın.

## <a name="remarks"></a>Açıklamalar

Komut satırında birden çok **`/MANIFESTUAC`** seçenek belirtirseniz, en son girilen bir önceliğe sahip olur.

Seçenekleri aşağıdaki gibidir **`/MANIFESTUAC:`** _`level`_ :

- **`level='asInvoker'`**: Uygulama, başlatan işlemle aynı izin düzeyinde çalışır. **Yönetici olarak çalıştır**' i seçerek uygulamayı daha yüksek bir izin düzeyine yükseledebilirsiniz.

- **`level='highestAvailable'`**: Uygulama, mümkün olan en yüksek izin düzeyinde çalışır. Uygulamayı başlatan kullanıcı Yöneticiler grubunun bir üyesiyse, bu seçenek ile aynıdır **`level='requireAdministrator'`** . En yüksek kullanılabilir izin düzeyi, açma işleminin düzeyinden yüksekse, sistem kimlik bilgilerini ister.

- **`level='requireAdministrator'`**: Uygulama yönetici izinleri kullanılarak çalışır. Uygulamayı başlatan kullanıcı Yöneticiler grubunun bir üyesi olmalıdır. Açma işlemi yönetimsel izinlerle çalışmıyorsa, sistem kimlik bilgilerini ister.

*`level`* *`uiAccess`* Seçeneğini kullanarak, ve değerlerini tek bir adımda belirtebilirsiniz **`/MANIFESTUAC:`** _`fragment`_ . Parça aşağıdaki biçimde olmalıdır:

> **`/MANIFESTUAC:`** \[ **`"`** ] **`level=`** { **`'asInvoker'`** | **`'highestAvailable'`** | **`'requireAdministrator'`** } **`uiAccess=`** { **`'true'`** | **`'false'`** } \[ **`"`** ]

Örneğin:

**`/MANIFESTUAC:"level='highestAvailable' uiAccess='true'"`**

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **bağlayıcı**  >  **bildirim dosyası** özellik sayfasını seçin.

1. **Kullanıcı hesabı denetimini etkinleştir (UAC)**, **UAC yürütme düzeyi** ve **UAC Kullanıcı arabirimi koruma özelliklerini atlayın** .

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

1. Bkz <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.EnableUAC%2A> <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.UACExecutionLevel%2A> ., ve <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.UACUIAccess%2A> .

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)
