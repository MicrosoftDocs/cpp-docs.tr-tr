---
title: "Nasıl yapılır: sembolleri kaynaklarda arama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- symbols, finding
- resources [Visual Studio], searching for symbols
ms.assetid: 6efef8e8-d0d4-4c49-b895-314974e7791a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 154c7a7284272ceef7a3e2d82fcd90d05069b7fe
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-search-for-symbols-in-resources"></a>Nasıl Yapılır: Sembolleri Kaynaklarda Arama
### <a name="to-find-symbols-in-resources"></a>Simgeleri kaynakları bulmak için  
  
1.  Gelen **Düzenle** menüsünde seçin **Find Symbol**.  
  
2.  İçinde [sembol Bul iletişim kutusu](http://msdn.microsoft.com/en-us/63e93d9c-784f-418d-a76a-723da5ff5d96), **Aranan** kutusunda, önceki arama dizesi aşağı açılan listeden seçin veya yazın (örneğin, ID_ACCEL1) bulmak istediğiniz kısayol tuşu.  
  
    > [!TIP]
    >  Kullanılacak [normal ifadeler](/visualstudio/ide/using-regular-expressions-in-visual-studio) aramanız için kullanmanız gerekir [dosyalarda Bul komutu](/visualstudio/ide/reference/find-command) gelen **Düzenle** menü yerine **Find Symbol**komutu. Normal ifadeler etkinleştirmek için bilmeniz gereken **kullanın: normal ifadeler** onay kutusu seçili [Bul iletişim kutusu](http://msdn.microsoft.com/en-us/dad03582-4931-4893-83ba-84b37f5b1600). Sağ tarafındaki sağ ok düğmesine tıklayın ardından **Aranan** kutusunu normal arama ifadeleri listesini görüntüleyin. Bu listeden bir ifade seçtiğinizde, arama metin olarak geçmesidir **Aranan** kutusu.  
  
3.  Birini seçin **Bul** seçenekleri.  
  
4.  Tıklatın **Sonrakini Bul**.  
  
    > [!NOTE]
    >  Dize, Hızlandırıcı veya ikili kaynaklar sembolleri arama yapamazsınız.  
  
 Kaynakları yönetilen projelerine ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakları](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu.* Kaynak dosyaları el ile yönetilen projelerine ekleme, kaynaklara erişme, statik kaynaklarını görüntüleme ve özellikleri için kaynak dizeleri atama hakkında bilgi için ve [izlenecek yol: kullanarak kaynakları yerelleştirme ASP.NETile](http://msdn.microsoft.com/Library/bb4e5b44-e2b0-48ab-bbe9-609fb33900b6).  
  
 **Gereksinimler**  
  
 Win32  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Semboller: Kaynak tanımlayıcılar](../windows/symbols-resource-identifiers.md)   
 [Kaynak dosyaları](../windows/resource-files-visual-studio.md)   
 [Kaynak Düzenleyicileri](../windows/resource-editors.md)