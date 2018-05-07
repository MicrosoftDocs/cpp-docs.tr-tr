---
title: COM arabirimi (Visual C++) oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.codewiz.com.creating.interfaces
dev_langs:
- C++
helpviewer_keywords:
- COM interfaces, creating
ms.assetid: 1be84d3c-6886-4d1e-8493-56c4d38a96d4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d2844e9051c5e6adf14085bcd7bfcd8096c6f8f7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="creating-a-com-interface-visual-c"></a>COM Arabirimi Oluşturma (Visual C++)
Visual C++ sihirbazları ve şablonları kullanan COM tanımlama arabirimleri ve dispinterfaces COM nesneleri ve Otomasyon sınıfları için proje oluşturmak için sağlar.  
  
 Bu sihirbaz, aşağıdaki üç ortak görevleri gerçekleştirmek için kullanabilirsiniz:  
  
-   [MFC Projenize ATL Desteği Ekleme](../mfc/reference/adding-atl-support-to-your-mfc-project.md)  
  
     Kullanarak bir MFC projesi oluşturduktan sonra MFC Uygulama ATL desteği ekleme [MFC Uygulama Sihirbazı'nı](../mfc/reference/mfc-application-wizard.md) ve daha sonra çalıştırmayı **MFC ATL desteği ekleme** kod Sihirbazı. Bu destek eklenmiş bir MFC yürütülebilir veya DLL projesi yalnızca basit COM nesnelerine uygulanır. Bu ATL nesneleri birden çok arabirimlere sahip olabilir.  
  
-   [MFC ActiveX Denetimi Oluşturma](../mfc/reference/creating-an-mfc-activex-control.md)  
  
     Açık [MFC ActiveX Denetim Sihirbazı](../mfc/reference/mfc-activex-control-wizard.md) bir görüntüleme arabirimi ve sırasıyla .idl dosya ve denetim sınıfı içinde tanımlanan bir olay eşlemesi ile bir ActiveX denetimi oluşturulamıyor.  
  
-   [ATL Denetimi Ekleme](../atl/reference/adding-an-atl-control.md)  
  
     Bir birleşimini kullanmak [ATL Proje Sihirbazı](../atl/reference/atl-project-wizard.md) ve [ATL Denetim Sihirbazı](../atl/reference/atl-control-wizard.md) ATL ActiveX denetimi oluşturulamıyor.  
  
     MFC projesinde ATL desteği, eklediğiniz yukarıda açıklandığı gibi bir ATL denetimi ekleyebilirsiniz. Ayrıca, seçerseniz **ATL Denetim** içinde **sınıfı Ekle** iletişim kutusu ve değil henüz eklediğiniz ATL desteği, MFC projenize, Visual Studio ekleme ATL desteği onaylayan bir iletişim kutusu görüntüler, MFC projesi.  
  
     Bu sihirbaz, proje sınıflarda IDL kaynak ve COM eşlemesi oluşturur.  
  
 ATL projesinde açın, sonra [sınıfı Ekle](../ide/add-class-dialog-box.md) iletişim kutusunda, ek sihirbazlar ve şablonlar COM arabirimleri projenize eklemek için seçimi verir. Aşağıdaki sihirbazlar için bir veya daha fazla arayüzleri kurmanızı izin ver:  
  
-   [ATL COM+ 1.0 Bileşeni Sihirbazı](../atl/reference/atl-com-plus-1-0-component-wizard.md)  
  
-   [ATL Basit Nesne Sihirbazı](../atl/reference/atl-simple-object-wizard.md)  
  
-   [ATL Active Server Page Bileşeni Sihirbazı](../atl/reference/atl-active-server-page-component-wizard.md)  
  
-   [ATL Denetimi Sihirbazı](../atl/reference/atl-control-wizard.md)  
  
 Ayrıca, nesnenin control sınıfı Sınıf Görünümü'nde sağ tıklatıp, COM denetimi yeni arabirimleri uygulayabileceğiniz [arabirimini uygulayan](../ide/implement-interface-wizard.md).  
  
> [!NOTE]
>  Visual Studio Proje için bir arabirim eklemek için bir sihirbaz sağlamaz. ATL projesinde ya da çok arabirim ekleyebileceğiniz bir [MFC projenize ATL desteği ekleme](../mfc/reference/adding-atl-support-to-your-mfc-project.md) kullanarak basit bir nesne ekleyerek [ATL Basit Nesne Sihirbazı](../atl/reference/atl-simple-object-wizard.md). Alternatif olarak, projenin .idl dosyasını açın ve yazarak arabirimi oluşturun:  
  
```  
interface IMyInterface {  
};  
  
```  
  
 Bkz: [arabirimi uygulama](../ide/implementing-an-interface-visual-cpp.md) ve [nesneleri ekleme ve denetimleri için ATL projesinde](../atl/reference/adding-objects-and-controls-to-an-atl-project.md) daha fazla bilgi için.  
  
 Visual C++ görüntülemek için çeşitli yollar sağlar ve [COM arabirimleri Düzenle](../ide/editing-a-com-interface.md) projeleriniz için tanımlanmış. [Sınıf Görünümü](http://msdn.microsoft.com/en-us/8d7430a9-3e33-454c-a9e1-a85e3d2db925) herhangi bir arabirim veya C++ projenizi .idl dosyasında tanımlanan görüntüleme arabirimi simgelerini görüntüler.  
  
 ATL tabanlı COM nesne sınıfları için sınıf görünümü ATL sınıfı ve bunu uygulayan arabirimleri arasındaki ilişkiyi görüntülemek için ATL sınıfı COM eşlemesinde okur.  
  
 Sınıf Görünümü ve kısayol menülerini arabirimleriyle gibi çözüm bulabilirsiniz:  
  
-   ATL nesneleri için MFC tabanlı bir uygulama ekleyin.  
  
-   Yöntemler, özellikler ve olaylar ekleyin.  
  
-   Bir öğenin arabirimi kodu doğrudan öğeyi çift tıklatarak geçin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Uygulama sihirbazları kullanarak masaüstü projeleri oluşturma](../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [Kod sihirbazlarıyla işlevsellik ekleme](../ide/adding-functionality-with-code-wizards-cpp.md)