---
title: "Semboller: Kaynak tanımlayıcılar | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.editors.symbol.identifiers
dev_langs:
- C++
helpviewer_keywords:
- symbols, resource identifiers
- symbols, creating
- resource symbols
- symbols, editing
- resource editors, resource symbols
ms.assetid: 8fccc09a-0237-4a65-b9c4-57d60c59e324
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 931ec9cb5d7e756d47a24c0c2b30b8686cd0fd4c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="symbols-resource-identifiers"></a>Semboller: Kaynak Tanımlayıcılar
Bir simge olan iki bölümden oluşan bir kaynak tanımlayıcısı (ID): bir tamsayı değeri (sembol değeri) eşlenen bir metin dizesi (sembol adı). Örneğin:  
  
```  
IDC_EDITNAME = 5100  
```  
  
 Sembol adları, en sık tanımlayıcıları da adlandırılır.  
  
 Simgeler kaynaklara ve kullanıcı arabirimi nesneleri, hem kaynak kodunuz ve bunlarla kaynak düzenleyicileri çalışırken başvuran, açıklayıcı bir yolunu sağlar. Görüntüleyin ve bir uygun bir yer kullanarak simgeleri işlemek [kaynak sembolleri iletişim kutusu](../windows/viewing-resource-symbols.md).  
  
 Yeni bir kaynak veya kaynak nesnesi oluşturduğunuzda [kaynak düzenleyicileri](../windows/resource-editors.md) varsayılan için bir kaynak, örneğin, ad `IDC_RADIO1`ve bir değere atayın. Name değeri plus tanımı Resource.h dosyasında depolanır.  
  
> [!NOTE]
>  Kaynakları veya kaynak nesneleri bir .rc dosyasından diğerine kopyalarken, Visual C++ aktarılan kaynağın sembol değeri veya sembol adını ve sembol adları veya var olan dosyayı değerleri ile çakışmaları önlemek için değer değişebilir.  
  
 Bu nedenle uygulamanız boyutu ve açıdan çok yönlülük büyüdükçe, kaynakları ve simgeleri sayısı yapar. Çok sayıda pek çok dosya dağılmış simgeleri izleme zor olabilir. [Kaynak sembolleri iletişim kutusu](../windows/resource-symbols-dialog-box.md) üzerinden yapabilecekleriniz merkezi bir aracı sunarak simgesi yönetimini kolaylaştırır:  
  
- [Görünüm kaynak semboller](../windows/viewing-resource-symbols.md)  
  
- [Yeni semboller oluşturma](../windows/creating-new-symbols.md)  
  
- [Atanmamış sembolleri değiştirme](../windows/changing-unassigned-symbols.md)  
  
- [Atanmamış sembolleri silme](../windows/deleting-unassigned-symbols.md)  
  
- [Belirli bir sembol için kaynak düzenleyicisini açın](../windows/opening-the-resource-editor-for-a-given-symbol.md)  
  
- [Sembolü veya sembol adını (ID) değiştirme](../windows/changing-a-symbol-or-symbol-name-id.md)  
  
- [Sembolün sayısal değerini değiştirin](../windows/changing-a-symbol-s-numeric-value.md)  
  
- [Sembol başlık dosyalarının adlarını değiştirme](../windows/changing-the-names-of-symbol-header-files.md)  
  
- [İçerir (salt okunur) paylaşılan veya hesaplanan sembolleri ekleme](../windows/including-shared-read-only-or-calculated-symbols.md)  
  
- [Önceden tanımlanmış sembol kimlikleri görüntüleyin](../windows/predefined-symbol-ids.md)  
  
 Kaynakları yönetilen projelerine ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakları](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu.* Kaynak dosyaları el ile yönetilen projelerine ekleme, kaynaklara erişme, statik kaynaklarını görüntüleme ve özellikleri için kaynak dizeleri atama hakkında daha fazla bilgi için bkz: [Masaüstü uygulamaları için kaynak dosyalar oluşturma](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamaları yerelleştirme](/dotnet/standard/globalization-localization/index).  
  
## <a name="requirements"></a>Gereksinimler  
 Win32  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: sembolleri kaynaklarda arama](../windows/how-to-search-for-symbols-in-resources.md)   
 [Kaynak düzenleyicileri](../windows/resource-editors.md)   
 [Kaynak dosyaları](../windows/resource-files-visual-studio.md)

