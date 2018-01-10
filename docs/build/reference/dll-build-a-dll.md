---
title: -DLL (DLL derleme) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /dll
dev_langs: C++
helpviewer_keywords:
- -DLL linker option
- /DLL linker option [C++]
- exporting DLLs [C++], specifying exports
- DLLs [C++], building
- DLL linker option [C++]
ms.assetid: c7685aec-31d0-490f-9503-fb5171a23609
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 28a501590e127e5f27a465366611b4dbf3be175c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="dll-build-a-dll"></a>/DLL (DLL Derleme)
```  
/DLL  
```  
  
## <a name="remarks"></a>Açıklamalar  
 / DLL seçeneği DLL ana çıktı dosyası oluşturur. DLL genellikle başka bir program tarafından kullanılan dışarı içerir. Önerilen Kullanım sırasına göre listelenen dışarı aktarmaları belirtme için üç yöntem vardır:  
  
1.  [__declspec(dllexport)](../../cpp/dllexport-dllimport.md) kaynak kodu  
  
2.  Bir [dışarı](../../build/reference/exports.md) .def dosyası deyimi  
  
3.  Bir [/dışarı aktarma](../../build/reference/export-exports-a-function.md) bağlantı komutunda belirtimi  
  
 Bir program birden fazla yöntemini kullanabilirsiniz.  
  
 DLL oluşturmak için başka bir yolu **Kitaplığı** modül tanımlama deyimi. /BASE ve/dll seçenekler birbirine eşit olan **Kitaplığı** deyimi.  
  
 Geliştirme ortamı içinde bu seçeneği belirtmeyin; Bu seçenek yalnızca komut satırı kullanımı için geçerlidir. Bir uygulama sihirbazıyla DLL projesi oluşturduğunuzda, bu seçeneği ayarlayın.  
  
 .dll oluşturmadan önce ilk adım, içeri aktarma kitaplığını oluşturursanız, içeri aktarma kitaplığını oluştururken geçirilen gibi aynı nesne dosyaları kümesini .dll oluştururken geçmesi gerektiğini unutmayın.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **yapılandırma özellikleri** klasör.  
  
3.  Tıklatın **genel** özellik sayfası.  
  
4.  Değiştirme **yapılandırma türü** özelliği.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCPropertySheet.ConfigurationType%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)