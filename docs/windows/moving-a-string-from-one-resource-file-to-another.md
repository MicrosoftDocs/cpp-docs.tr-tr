---
title: Bir dizeyi bir kaynak dosyasından diğerine taşıma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- strings [C++], moving between files
- resource script files, moving strings
- string editing, moving strings between resources
- String editor, moving strings between files
ms.assetid: 94f8ee81-9b4c-4788-ba95-68c58db38029
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1481f04b88d6ab63486885d93b971c3023d3e0d2
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33879275"
---
# <a name="moving-a-string-from-one-resource-file-to-another"></a>Dizeyi Bir Kaynak Dosyasından Diğerine Taşıma
### <a name="to-move-a-string-from-one-resource-script-file-to-another"></a>Bir dizeyi bir kaynak betik dosyasından diğerine taşımak için  
  
1.  Dize tabloları hem .rc dosyaları açın. (Daha fazla bilgi için bkz: [kaynaklar görüntüleme, bir kaynak betik dosyası dışında of proje](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md).)  
  
    > [!NOTE]
    >  Projenizi bir .rc dosyası yoksa, lütfen bkz [yeni bir kaynak betik dosyası oluşturma](../windows/how-to-create-a-resource-script-file.md).  
  
2.  Taşıma ve seçmek istediğiniz dize sağ **Kes** kısayol menüsünden.  
  
3.  Hedef imleci yerleştirin **Dize Düzenleyicisi** penceresi.  
  
4.  Dize taşımak istediğiniz .rc dosyasına sağ tıklayın ve seçin **Yapıştır** kısayol menüsünden.  
  
    > [!NOTE]
    >  Varsa **kimliği** veya **değeri** varolan taşınan dize çakışmalarını **kimliği** veya **değeri** hedef dosyadaki ya da **Kimliği** veya **değeri** taşınan dize değişiklikleri. Bir dize ile aynı olup olmadığını **kimliği**, **kimliği** taşınan dize değişiklikleri. Bir dize ile aynı olup olmadığını **değeri**, **değeri** taşınan dize değişiklikleri.  
  
 Kaynakları yönetilen projelere (olanlar ortak dil çalışma zamanı hedef) ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakları](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu.* Kaynak dosyaları el ile yönetilen projelerine ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynakları dizeleri özelliklerine atama hakkında daha fazla bilgi için bkz: [izlenecek yol: Windows Formları yerelleştirme](http://msdn.microsoft.com/en-us/9a96220d-a19b-4de0-9f48-01e5d82679e5) ve [İzlenecek yol: ASP.NET ile yerelleştirme kaynaklarını kullanan](http://msdn.microsoft.com/Library/bb4e5b44-e2b0-48ab-bbe9-609fb33900b6).  
  
 **Gereksinimler**  
  
 Win32  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dize Düzenleyicisi](../windows/string-editor.md)   
 [Kaynak dosyaları](../windows/resource-files-visual-studio.md)   
 [Pencere düzenlerini özelleştirme](/visualstudio/ide/customizing-window-layouts-in-visual-studio)   

