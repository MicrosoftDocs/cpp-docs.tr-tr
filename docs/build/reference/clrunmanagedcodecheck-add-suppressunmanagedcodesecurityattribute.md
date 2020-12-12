---
description: Daha fazla bilgi edinin:/CLRUNMANAGEDCODECHECK (SuppressUnmanagedCodeSecurityAttribute 'i Kaldır)
title: /CLRUNMANAGEDCODECHECK (SuppressUnmanagedCodeSecurityAttribute çıkar)
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
ms.openlocfilehash: e08b7b4b18a463122316b041ad81d6ddd2598bca
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97182404"
---
# <a name="clrunmanagedcodecheck-remove-suppressunmanagedcodesecurityattribute"></a>/CLRUNMANAGEDCODECHECK (SuppressUnmanagedCodeSecurityAttribute çıkar)

**/CLRUNMANAGEDCODECHECK** , bağlayıcının <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> `PInvoke` yönetilen koddan yerel dll 'lere bağlayıcı tarafından oluşturulan çağrılar için uygulanacağını belirtir.

## <a name="syntax"></a>Syntax

> **/CLRUNMANAGEDCODECHECK**[**: No**]

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak bağlayıcı, **SuppressUnmanagedCodeSecurityAttribute** öğesini bağlayıcı tarafından oluşturulan `PInvoke` çağrılara uygular. **/CLRUNMANAGEDCODECHECK** etkin olduğunda, **SuppressUnmanagedCodeSecurityAttribute** kaldırılır. **SuppressUnmanagedCodeSecurityAttribute** 'ı bağlayıcı tarafından oluşturulan çağrılara açık bir şekilde uygulamak için `PInvoke` **/CLRUNMANAGEDCODECHECK: No** komutunu kullanabilirsiniz.

Bağlayıcı, özniteliği yalnızca **/clr** veya **/clr: Pure** kullanılarak derlenen nesnelere ekler. Ancak, **/clr: Pure** derleyici seçeneği visual Studio 2015 ' de kullanımdan kaldırılmıştır ve visual Studio 2017 ve sonrasında desteklenmez.

`PInvoke`Bağlayıcı yönetilen bir çağıranın başvurusunu karşılamak için yönetilen bir sembol bulamadığında, ancak bu başvuruyu karşılamak için yerel bir sembol bulamadığında, bir çağrı bağlayıcı tarafından oluşturulur. Hakkında daha fazla bilgi için `PInvoke` bkz. [yönetilen koddan yerel işlevleri çağırma](../../dotnet/calling-native-functions-from-managed-code.md).

<xref:System.Security.AllowPartiallyTrustedCallersAttribute>Kodunuzda kullanıyorsanız, **SuppressUnmanagedCodeSecurity** özniteliğini kaldırmak için açıkça **/CLRUNMANAGEDCODECHECK** ' i ayarlamanız gerektiğini unutmayın. Bir görüntü hem **SuppressUnmanagedCodeSecurity** hem de **Allowpartiallytrustedçağıranlar** özniteliklerini içeriyorsa, bu olası bir güvenlik açığıdır.

**SuppressUnmanagedCodeSecurityAttribute** kullanmanın etkileri hakkında daha fazla bilgi için bkz. [yönetilmeyen kod Için güvenli kodlama yönergeleri](/dotnet/framework/security/secure-coding-guidelines-for-unmanaged-code) .

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri** düğümünü genişletin.

1. **Bağlayıcı** düğümünü genişletin.

1. **Gelişmiş** özellik sayfasını seçin.

1. **Clr yönetilmeyen kod denetimi** özelliğini değiştirin.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

1. Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.CLRUnmanagedCodeCheck%2A>.

## <a name="see-also"></a>Ayrıca bkz.

- [MSVC bağlayıcı başvurusu](linking.md)
- [MSVC bağlayıcı seçenekleri](linker-options.md)
