---
title: / CLRUNMANAGEDCODECHECK (SuppressUnmanagedCodeSecurityAttribute Ekle) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /CLRUNMANAGEDCODECHECK
dev_langs:
- C++
helpviewer_keywords:
- -CLRUNMANAGEDCODECHECK linker option
- /CLRUNMANAGEDCODECHECK linker option
ms.assetid: 73abc426-dab0-45e2-be85-0f9a14206cc2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 679adc527cc70056e1292eb7e639499bd814bca6
ms.sourcegitcommit: 7838764e09819822a105accf5d773b2e37ffa0ae
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/28/2018
ms.locfileid: "47429767"
---
# <a name="clrunmanagedcodecheck-add-suppressunmanagedcodesecurityattribute"></a>/ CLRUNMANAGEDCODECHECK (SuppressUnmanagedCodeSecurityAttribute ekleme)

**/ CLRUNMANAGEDCODECHECK** bağlayıcı uygulayıp uygulamayacağını belirtir <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> için bağlayıcı tarafından oluşturulan `PInvoke` yönetilen koddan yerel DLL'lere çağrılar.

## <a name="syntax"></a>Sözdizimi

> **/ CLRUNMANAGEDCODECHECK**[**: NO**]

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bağlayıcı uygular **SuppressUnmanagedCodeSecurityAttribute** için bağlayıcı tarafından oluşturulan `PInvoke` çağırır. Zaman **/clrunmanagedcodecheck** kıyaslandığında geçerli **SuppressUnmanagedCodeSecurityAttribute** uygulanmaz.

Bağlayıcı yalnızca ile derlenen nesneler bir öznitelik ekler. **/CLR** veya **/CLR: pure**. Ancak, **/CLR: pure** derleyici seçeneğini Visual Studio 2015'te kullanım dışı ve Visual Studio 2017'de desteklenmiyor.

A `PInvoke` çağrı, bağlayıcı tarafından oluşturulur, bağlayıcı yönetilen çağıran bir başvurudan karşılamak için yönetilen bir sembolü bulunamadı, ancak bu başvuruyu karşılamak için bir yerel sembol bulabilirsiniz. Hakkında daha fazla bilgi için `PInvoke`, bkz: [yönetilen koddan yerel işlevleri çağırma](../../dotnet/calling-native-functions-from-managed-code.md).

Kullandığınız gerçekleştiriyorsanız <xref:System.Security.AllowPartiallyTrustedCallersAttribute> kodunuzda açıkça ayarlamalısınız **/clrunmanagedcodecheck**. Görüntü SuppressUnmanagedCodeSecurity hem AllowPartiallyTrustedCallers öznitelikleri içeriyorsa, olası güvenlik açığı var.

Bkz: [güvenli kodlama kılavuzları yönetilmeyen kod için](/dotnet/framework/security/secure-coding-guidelines-for-unmanaged-code) kullanmanın etkileri hakkında daha fazla bilgi için **SuppressUnmanagedCodeSecurityAttribute**.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Genişletin **yapılandırma özellikleri** düğümü.

1. Genişletin **bağlayıcı** düğümü.

1. Seçin **Gelişmiş** özellik sayfası.

1. Değiştirme **CLR yönetilmeyen kod denetleyin** özelliği.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

1. Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.CLRUnmanagedCodeCheck%2A>.

## <a name="see-also"></a>Ayrıca bkz.

- [Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)
- [Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)
