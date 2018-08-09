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
ms.openlocfilehash: ab47494f18bfca8a94e6fc4697cf354eb71c5321
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40014093"
---
# <a name="moving-a-string-from-one-resource-file-to-another"></a>Dizeyi Bir Kaynak Dosyasından Diğerine Taşıma
### <a name="to-move-a-string-from-one-resource-script-file-to-another"></a>Bir dizeyi bir kaynak betik dosyasını diğerine taşımak için  
  
1.  Dize tabloları içinde her iki .rc dosyası açın. (Daha fazla bilgi için [kaynaklar içinde bir kaynak betik dosyası dışında sonuna bir proje görüntüleme](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md).)  
  
    > [!NOTE]
    >  Projenize bir .rc dosyası yoksa, lütfen bkz [yeni bir kaynak betik dosyası oluşturma](../windows/how-to-create-a-resource-script-file.md).  
  
2.  Sağ tıklayın, istediğiniz Taşı ve dize **Kes** kısayol menüsünden.  
  
3.  Hedef imleci **Dize Düzenleyicisi** penceresi.  
  
4.  Dize taşımak istediğiniz .rc dosyasına sağ tıklayın ve seçin **Yapıştır** kısayol menüsünden.  
  
    > [!NOTE]
    >  Varsa **kimliği** veya **değer** ile varolan taşınan dize çakışmalar **kimliği** veya **değer** hedef dosyasında ya da **Kimliği** veya **değer** taşınan dize değişiklikleri. Bir dize ile aynı varsa **kimliği**, **kimliği** taşınan dize değişiklikleri. Bir dize ile aynı varsa **değer**, **değer** taşınan dize değişiklikleri.  
  
 Yönetilen projelere kaynak (Bu ortak dil çalışma zamanını hedefleyen) ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [izlenecek yol: Windows formlarını yerelleştirme](http://msdn.microsoft.com/9a96220d-a19b-4de0-9f48-01e5d82679e5) ve [İzlenecek yol: ASP.NET ile yerelleştirme için kaynakların kullanarak](http://msdn.microsoft.com/Library/bb4e5b44-e2b0-48ab-bbe9-609fb33900b6).  
  
## <a name="requirements"></a>Gereksinimler  
 Win32  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dize Düzenleyicisi](../windows/string-editor.md)   
 [Kaynak dosyaları](../windows/resource-files-visual-studio.md)   
 [Pencere düzenlerini özelleştirme](/visualstudio/ide/customizing-window-layouts-in-visual-studio)   