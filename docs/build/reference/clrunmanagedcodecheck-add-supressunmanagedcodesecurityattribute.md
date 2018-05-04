---
title: -CLRUNMANAGEDCODECHECK (SupressUnmanagedCodeSecurityAttribute ekleme) | Microsoft Docs
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
ms.openlocfilehash: a00563460519225b38b1c5e745679da943d890cd
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="clrunmanagedcodecheck-add-supressunmanagedcodesecurityattribute"></a>/CLRUNMANAGEDCODECHECK (SupressUnmanagedCodeSecurityAttribute Ekleme)
**/ CLRUNMANAGEDCODECHECK** bağlayıcı uygulanıp uygulanmayacağını belirtir <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> bağlayıcı-oluşturulan `PInvoke` Yerel DLL'leri yönetilen koddan çağrılar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/CLRUNMANAGEDCODECHECK[:NO]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bağlayıcı tarafından oluşturulan varsayılan olarak, bağlayıcı SuppressUnmanagedCodeSecurityAttribute uygular `PInvoke` çağrıları. Zaman **/CLRUNMANAGEDCODECHECK** , SuppressUnmanagedCodeSecurityAttribute uygulanmamış etkindir.  
  
 Bağlayıcı yalnızca ile derlenmiş nesneleri bir öznitelik ekler. **/CLR** veya **/CLR: pure**. Ancak, **/CLR: pure** ve **/CLR: safe** derleyici seçenekleri Visual Studio 2015'te kullanım dışı bırakılmış ve derleyici gelecek bir sürümünde kaldırılacak.  
  
 A `PInvoke` çağrısı, bağlayıcı tarafından üretilir, bağlayıcı yönetilen çağıran bir başvuru karşılamak için yönetilen bir simge bulunamıyor ancak bu başvuruyu karşılamak için yerel bir simge bulabilirsiniz. Hakkında daha fazla bilgi için `PInvoke`, bkz: [yönetilen koddan yerel işlevleri çağırma](../../dotnet/calling-native-functions-from-managed-code.md).  
  
 Kullandığınız gerçekleştiriyorsanız <xref:System.Security.AllowPartiallyTrustedCallersAttribute> kodunuzda, açıkça ayarlamalısınız **/CLRUNMANAGEDCODECHECK**. Bir görüntü SuppressUnmanagedCodeSecurity ve AllowPartiallyTrustedCallers öznitelikleri içeriyorsa, olası güvenlik açığı bulunmaktadır.  
  
 Bkz: [güvenli kodlama yönergeleri yönetilmeyen kod için](/dotnet/framework/security/secure-coding-guidelines-for-unmanaged-code) SuppressUnmanagedCodeSecurityAttribute kullanarak etkilerini hakkında daha fazla bilgi.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Genişletme **yapılandırma özellikleri** düğümü.  
  
3.  Genişletme **bağlayıcı** düğümü.  
  
4.  Seçin **Gelişmiş** özellik sayfası.  
  
5.  Değiştirme **CLR kodu yönetilmeyen kontrol** özelliği.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için  
  
1.  Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.CLRUnmanagedCodeCheck%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)