---
title: Kaynak dosyalar (Visual Studio) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- resources [Visual Studio]
- .rc files
- resource files
- resource script files
- resource script files, Win-32 based applications
- resource script files, files updated when editing resources
- resources [Visual Studio], types of resource files
- rct files
- resources [C++]
- rc files
- resource files, types of
- .rct files
- resource script files, unsupported types
ms.assetid: 4d2b6fcc-07cf-4289-be87-83a60f69533c
caps.latest.revision: "18"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 1e1ff029c2fb7a39c0257358ebb1f73f53ca3837
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="resource-files-visual-studio"></a>Kaynak Dosyalar (Visual Studio)
> [!NOTE]
>  Bu yazıda Windows Masaüstü uygulamaları için geçerlidir. Evrensel Windows platformu uygulamaları kaynakları hakkında daha fazla bilgi için bkz: [tanımlama uygulama kaynakları](http://msdn.microsoft.com/en-us/476ea844-632c-4467-9ce3-966be1350dd4).  
>   
> Kaynakları yönetilen projelerine ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakları](https://msdn.microsoft.com/library/f45fce5x.aspx) içinde *.NET Framework Geliştirici Kılavuzu.* Kaynak dosyaları el ile yönetilen projelerine ekleme, kaynaklara erişme, statik kaynaklarını görüntüleme ve özellikleri için kaynak dizeleri atama hakkında daha fazla bilgi için bkz: [Masaüstü uygulamaları için kaynak dosyalar oluşturma](https://msdn.microsoft.com/library/xbx3z216.aspx). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamaları yerelleştirme](https://msdn.microsoft.com/library/h6270d0z.aspx).  
>  
> .NET programlama dilleri projelerde kaynak betik dosyaları kullanmayın beri kaynaklarınızdan açmalısınız **Çözüm Gezgini**. Kullanabileceğiniz [görüntü Düzenleyicisi](../windows/image-editor-for-icons.md) ve [İkili Düzenleyicisi](binary-editor.md) yönetilen projelerde kaynak dosyalarıyla çalışmak için. Düzenlemek istediğiniz yönetilen kaynaklar, bağlı kaynaklar olmalıdır. Visual Studio kaynak düzenleyicileri eklenmiş kaynakları düzenlemeyi desteklemez.  
  
 "Kaynak dosyası" terimini de dahil olmak üzere dosya türlerinin bir sayıya başvurabilir:  
  
-   Bir programın kaynak komut dosyası (.rc) dosyası.  
  
-   Bir kaynak şablonu (.rct) dosyası.  
  
-   Tek başına bir dosya olarak var olan tek bir kaynağın bir bit eşlem, simgesi veya imleci dosyası gibi bir .rc dosyasından bilinir.  
  
-   Örneğin bir .rc dosyasından başvurulan Resource.h, geliştirme ortamı tarafından oluşturulan bir üstbilgi dosyası.  
  
 Kaynaklar ayrıca bulunabilir [diğer dosya türleri](../windows/editable-file-types-for-resources.md) .exe, .dll ve .res dosyaları gibi. Kaynaklar ve kaynak dosyalarına projenizi ve geçerli projenin bir parçası olmayan dosyalarla çalışabilirsiniz. Visual Studio geliştirme ortamında oluşturulmayan kaynak dosyalarla çalışabilirsiniz. Örneğin, şunları yapabilirsiniz:  
  
-   İç içe geçmiş ve koşullu dahil kaynak dosyalarıyla birlikte çalışır.  
  
-   Var olan kaynakları güncelleştirme veya Visual C++ biçimine dönüştürebilirsiniz.  
  
-   İçeri aktarma veya için veya geçerli kaynak dosyadan grafik kaynakları verebilirsiniz.  
  
-   Geliştirme ortamı tarafından değiştirilemez paylaşılan veya salt okunur tanımlayıcıları (simge) içerir.  
  
-   Birkaç projeleri arasında paylaşılan kaynakları gibi geçerli projenize sırasında düzenleme gerektiren yok (veya düzenlenebilir istemediğiniz) kaynaklar yürütülebilir dosyanın (.exe) dosyası içerir.  
  
-   Geliştirme ortamı tarafından desteklenmeyen kaynak türleri içerir.  
  
 Bu bölümde ele alınmaktadır:  
  
-   [Yeni bir kaynak betik dosyası oluşturma](../windows/how-to-create-a-resource-script-file.md)  
  
-   [Yeni kaynak oluşturma](../windows/how-to-create-a-resource.md)  
  
-   [Kaynak betik dosyası kaynakları görüntüleme](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)  
  
-   [Kaynak betik dosyasını metin biçiminde açma](../windows/how-to-open-a-resource-script-file-in-text-format.md)  
  
-   [Derleme zamanı dahil olmak üzere kaynakları](../windows/how-to-include-resources-at-compile-time.md)  
  
-   [Kaynakları kopyalama](../windows/how-to-copy-resources.md)  
  
-   [Kaynak şablonları (.rct) kullanma](../windows/how-to-use-resource-templates.md)  
  
-   [İçeri ve dışarı aktarma kaynakları](../windows/how-to-import-and-export-resources.md)  
  
-   [Kaynaklar için düzenlenebilir dosya türleri](../windows/editable-file-types-for-resources.md)  
  
-   [Kaynak düzenlemesinden etkilenen dosyalar](../windows/files-affected-by-resource-editing.md)  
  
## <a name="requirements"></a>Gereksinimler  
 Win32  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak düzenleyicileri](../windows/resource-editors.md)   
 [Kaynak dosyaları ile çalışma](../windows/working-with-resource-files.md)   
 [Menüler ve diğer kaynaklar](http://msdn.microsoft.com/library/windows/desktop/ms632583.aspx)

