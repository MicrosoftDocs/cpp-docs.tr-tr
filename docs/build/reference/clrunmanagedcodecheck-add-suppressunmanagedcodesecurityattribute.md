---
title: / CLRUNMANAGEDCODECHECK (SuppressUnmanagedCodeSecurityAttribute Kaldır)
ms.date: 05/16/2019
ms.topic: reference
f1_keywords:
- /CLRUNMANAGEDCODECHECK
helpviewer_keywords:
- -CLRUNMANAGEDCODECHECK linker option
- /CLRUNMANAGEDCODECHECK linker option
ms.assetid: 73abc426-dab0-45e2-be85-0f9a14206cc2
author: corob-msft
ms.author: corob
ms.openlocfilehash: ecc560673a8e98752289ef0e0f89d3abfc1938e4
ms.sourcegitcommit: a10c9390413978d36b8096b684d5ed4cf1553bc8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/17/2019
ms.locfileid: "65837237"
---
# <a name="clrunmanagedcodecheck-remove-suppressunmanagedcodesecurityattribute"></a>/ CLRUNMANAGEDCODECHECK (SuppressUnmanagedCodeSecurityAttribute Kaldır)

**/ CLRUNMANAGEDCODECHECK** bağlayıcı uygulanmaz belirtir <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> için bağlayıcı tarafından oluşturulan `PInvoke` yönetilen koddan yerel DLL'lere çağrılar.

## <a name="syntax"></a>Sözdizimi

> **/ CLRUNMANAGEDCODECHECK**[**: NO**]

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bağlayıcı uygular **SuppressUnmanagedCodeSecurityAttribute** için bağlayıcı tarafından oluşturulan `PInvoke` çağırır. Zaman **/clrunmanagedcodecheck** kıyaslandığında geçerli **SuppressUnmanagedCodeSecurityAttribute** kaldırılır. Açıkça uygulamak için **SuppressUnmanagedCodeSecurityAttribute** için bağlayıcı tarafından oluşturulan `PInvoke` kullanabileceğiniz çağrıları **/CLRUNMANAGEDCODECHECK:NO**.

Bağlayıcı, yalnızca öznitelik kullanılarak derlenmiş nesneleri ekler **/CLR** veya **/CLR: pure**. Ancak, **/CLR: pure** derleyici seçeneğini Visual Studio 2015'te kullanım dışı ve Visual Studio 2017 ve sonraki sürümlerde desteklenmiyor.

A `PInvoke` çağrı, bağlayıcı tarafından oluşturulur, bağlayıcı yönetilen çağıran bir başvurudan karşılamak için yönetilen bir sembolü bulunamadı, ancak bu başvuruyu karşılamak için bir yerel sembol bulabilirsiniz. Hakkında daha fazla bilgi için `PInvoke`, bkz: [yönetilen koddan yerel işlevleri çağırma](../../dotnet/calling-native-functions-from-managed-code.md).

Kullandığınız gerçekleştiriyorsanız <xref:System.Security.AllowPartiallyTrustedCallersAttribute> kodunuzda açıkça ayarlamalısınız **/clrunmanagedcodecheck** kaldırmak için **SuppressUnmanagedCodeSecurity** özniteliği. Görüntü her ikisi de içeriyorsa, olası bir güvenlik açığı olan **SuppressUnmanagedCodeSecurity** ve **AllowPartiallyTrustedCallers** öznitelikleri.

Bkz: [güvenli kodlama kılavuzları yönetilmeyen kod için](/dotnet/framework/security/secure-coding-guidelines-for-unmanaged-code) kullanmanın etkileri hakkında daha fazla bilgi için **SuppressUnmanagedCodeSecurityAttribute**.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Genişletin **yapılandırma özellikleri** düğümü.

1. Genişletin **bağlayıcı** düğümü.

1. Seçin **Gelişmiş** özellik sayfası.

1. Değiştirme **CLR yönetilmeyen kod denetleyin** özelliği.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

1. Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.CLRUnmanagedCodeCheck%2A>.

## <a name="see-also"></a>Ayrıca bkz.

- [MSVC bağlayıcı başvurusu](linking.md)
- [MSVC Bağlayıcı Seçenekleri](linker-options.md)
