---
title: / CLRUNMANAGEDCODECHECK (Kaldır SuppressUnmanagedCodeSecurityAttribute) | Microsoft Docs
ms.custom: ''
ms.date: 09/27/2018
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
ms.openlocfilehash: 9868f0c35f4a988ac8e0aee8076f232f86c04afd
ms.sourcegitcommit: 072e12d6b7a242765bdcc9afe4a14a284ade01fc
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/26/2018
ms.locfileid: "50136280"
---
# <a name="clrunmanagedcodecheck-remove-suppressunmanagedcodesecurityattribute"></a>/ CLRUNMANAGEDCODECHECK (SuppressUnmanagedCodeSecurityAttribute Kaldır)

**/ CLRUNMANAGEDCODECHECK** bağlayıcı uygulanmaz belirtir <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> için bağlayıcı tarafından oluşturulan `PInvoke` yönetilen koddan yerel DLL'lere çağrılar.

## <a name="syntax"></a>Sözdizimi

> **/ CLRUNMANAGEDCODECHECK**[**: NO**]

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bağlayıcı uygular **SuppressUnmanagedCodeSecurityAttribute** için bağlayıcı tarafından oluşturulan `PInvoke` çağırır. Zaman **/clrunmanagedcodecheck** kıyaslandığında geçerli **SuppressUnmanagedCodeSecurityAttribute** kaldırılır. Açıkça uygulamak için **SuppressUnmanagedCodeSecurityAttribute** için bağlayıcı tarafından oluşturulan `PInvoke` kullanabileceğiniz çağrıları **/CLRUNMANAGEDCODECHECK:NO**.

Bağlayıcı, yalnızca öznitelik kullanılarak derlenmiş nesneleri ekler **/CLR** veya **/CLR: pure**. Ancak, **/CLR: pure** derleyici seçeneğini Visual Studio 2015'te kullanım dışı ve Visual Studio 2017'de desteklenmiyor.

A `PInvoke` çağrı, bağlayıcı tarafından oluşturulur, bağlayıcı yönetilen çağıran bir başvurudan karşılamak için yönetilen bir sembolü bulunamadı, ancak bu başvuruyu karşılamak için bir yerel sembol bulabilirsiniz. Hakkında daha fazla bilgi için `PInvoke`, bkz: [yönetilen koddan yerel işlevleri çağırma](../../dotnet/calling-native-functions-from-managed-code.md).

Kullandığınız gerçekleştiriyorsanız <xref:System.Security.AllowPartiallyTrustedCallersAttribute> kodunuzda açıkça ayarlamalısınız **/clrunmanagedcodecheck** kaldırmak için **SuppressUnmanagedCodeSecurity** özniteliği. Görüntü her ikisi de içeriyorsa, olası bir güvenlik açığı olan **SuppressUnmanagedCodeSecurity** ve **AllowPartiallyTrustedCallers** öznitelikleri.

Bkz: [güvenli kodlama kılavuzları yönetilmeyen kod için](/dotnet/framework/security/secure-coding-guidelines-for-unmanaged-code) kullanmanın etkileri hakkında daha fazla bilgi için **SuppressUnmanagedCodeSecurityAttribute**.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Genişletin **yapılandırma özellikleri** düğümü.

1. Genişletin **bağlayıcı** düğümü.

1. Seçin **Gelişmiş** özellik sayfası.

1. Değiştirme **CLR yönetilmeyen kod denetleyin** özelliği.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

1. Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.CLRUnmanagedCodeCheck%2A>.

## <a name="see-also"></a>Ayrıca bkz.

- [Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)
- [Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)
