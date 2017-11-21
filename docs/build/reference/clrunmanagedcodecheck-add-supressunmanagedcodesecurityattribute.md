---
title: -CLRUNMANAGEDCODECHECK (SupressUnmanagedCodeSecurityAttribute ekleme) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /CLRUNMANAGEDCODECHECK
dev_langs: C++
helpviewer_keywords:
- -CLRUNMANAGEDCODECHECK linker option
- /CLRUNMANAGEDCODECHECK linker option
ms.assetid: 73abc426-dab0-45e2-be85-0f9a14206cc2
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f4810da2a1dd24893a1e69a35091b3a7c89b527e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="clrunmanagedcodecheck-add-supressunmanagedcodesecurityattribute"></a>/CLRUNMANAGEDCODECHECK (SupressUnmanagedCodeSecurityAttribute Ekleme)
**/ CLRUNMANAGEDCODECHECK** bağlayıcı uygulanıp uygulanmayacağını belirtir <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> bağlayıcı-oluşturulan `PInvoke` Yerel DLL'leri yönetilen koddan çağrılar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/CLRUNMANAGEDCODECHECK[:NO]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bağlayıcı tarafından oluşturulan varsayılan olarak, bağlayıcı SuppressUnmanagedCodeSecurityAttribute uygular `PInvoke` çağrıları. Zaman **/CLRUNMANAGEDCODECHECK** , SuppressUnmanagedCodeSecurityAttribute uygulanmamış etkindir.  
  
 Bağlayıcı yalnızca ile derlenmiş nesneleri bir öznitelik ekler. **/CLR** veya **/CLR: pure**. Bağlayıcı oluşturmayacak `PInvoke` ile derlenmiş nesnelerde çağırır **/CLR: safe**. Daha fazla bilgi için bkz: [/CLR (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md). **/CLR: pure** ve **/CLR: safe** derleyici seçenekleri Visual Studio 2015'te kullanım dışı.  
  
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
 [Bağlayıcı seçenekleri](../../build/reference/linker-options.md)