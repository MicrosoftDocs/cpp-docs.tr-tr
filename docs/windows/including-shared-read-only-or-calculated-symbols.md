---
title: "Dahil olmak üzere paylaşılan (salt okunur) veya hesaplanan sembolleri ekleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.editors.symbol.shared.calculated
dev_langs:
- C++
helpviewer_keywords:
- symbols, read-only
- symbols, shared
- symbols, calculated
- read-only symbols
- symbol directives
- calculated symbols
- shared symbols
ms.assetid: 32b77faf-a066-4371-a072-9a5b84c0766d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: bf0beeb90e2d4c4d22f45322f881bb7a247acf12
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="including-shared-read-only-or-calculated-symbols"></a>Paylaşılan (Salt Okunur) veya Hesaplanan Sembolleri Ekleme
Geliştirme ortamı başka bir uygulama tarafından oluşturulan bir kaynak dosyasını okur ilk kez tüm eklenen üst bilgi dosyaları salt okunur olarak işaretler. Sonuç olarak, kullanabileceğiniz [kaynağını içeren iletişim kutusu](../windows/resource-includes-dialog-box.md) ek salt okunur sembol üstbilgi dosyaları eklemek için.  
  
 Salt okunur sembol tanımlarını kullanmak isteyebilirsiniz nedenlerinden biri, birkaç projeler arasında paylaşmak simge dosyaları içindir.  
  
 Sembol değeri tanımlamak için basit tamsayılar yerine ifadeleri kullanmak sembol tanımlarını mevcut kaynaklarla olduğunda dahil simge dosyaları de kullanabilirsiniz. Örneğin:  
  
```  
#define   IDC_CONTROL1 2100  
#define   IDC_CONTROL2 (IDC_CONTROL1+1)  
```  
  
 Ortam doğru olduğu sürece bu hesaplanan sembolleri yorumlar:  
  
-   Hesaplanan semboller bir salt okunur semboller dosyasında yerleştirilir.  
  
-   Kaynak dosyanızı Bu hesaplanan sembolleri zaten atanmış kaynaklar içeriyor.  
  
-   Sayısal ifade bekleniyor.  
  
> [!NOTE]
>  Bir dize veya sayısal ifade bekleniyorsa, ifade değerlendirilmez.  
  
### <a name="to-include-shared-read-only-symbols-in-your-resource-file"></a>Kaynak dosyanızı paylaşılan (salt okunur) simgeleri eklemek için  
  
1.  İçinde [kaynak görünümü](../windows/resource-view-window.md).rc dosyasını sağ tıklatın ve seçin [kaynağını içeren](../windows/resource-includes-dialog-box.md) kısayol menüsünden.  
  
    > [!NOTE]
    >  Projenizi bir .rc dosyası yoksa, lütfen bkz [yeni bir kaynak betik dosyası oluşturma](../windows/how-to-create-a-resource-script-file.md).  
  
2.  İçinde **salt okunur sembol yönergeleri** kutusunda, kullanmak **#include** derleyici yönergesi tutulması için salt okunur semboller istediğiniz dosyayı belirtin.  
  
     Normalde ana sembol üstbilgi dosyası tarafından kullanılan dosya adı olduğundan Resource.h, dosya çağırmayın.  
  
    > [!NOTE]
    >  **Önemli** salt okunur sembol yönergeleri kutuya yazın tam olarak yazarken kaynak dosyasında bulunur. Ne tür emin yazım veya sözdizimi hataları içermiyor.  
  
     Kullanım **salt okunur sembol yönergeleri** yalnızca sembol tanımlarını dosyalarıyla dahil etmek için kutusunu. Kaynak tanımları içermez; Aksi takdirde, yinelenen kaynak tanımları dosyası kaydedildiğinde oluşturulur.  
  
3.  Simgeler belirttiğiniz dosyasına yerleştirin.  
  
     Bu şekilde bulunan dosyalar sembolleri kaynak dosyayı her açtığınızda değerlendirilir, ancak dosyanızı kaydettiğinizde oldukları diskte değiştirilmez.  
  
4.  **Tamam**'ı tıklatın.  
  

  
 Gereksinimler  
  
 Win32  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sembol adı kısıtlamaları](../windows/symbol-name-restrictions.md)   
 [Sembol değeri kısıtlamaları](../windows/symbol-value-restrictions.md)   
 [Önceden tanımlanmış sembol kimlikleri](../windows/predefined-symbol-ids.md)   
 [Semboller: Kaynak Tanımlayıcıları](../windows/symbols-resource-identifiers.md)