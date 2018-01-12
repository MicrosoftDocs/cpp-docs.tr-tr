---
title: "MFC sınıf Ekleme Sihirbazı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.codewiz.class.mfc.simple.overview
dev_langs: C++
helpviewer_keywords:
- MFC Add Class Wizard
- wizards [MFC]
ms.assetid: ad3b0989-d307-43b2-9417-3f9a78889024
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b4c65785008c7257fc2f3714d9bf78395f4a8e40
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="mfc-add-class-wizard"></a>MFC Sınıf Ekleme Sihirbazı
Varolan bir MFC projesine bir sınıf ekleyin ya da bir sınıf MFC destekleyen bir ATL projesine eklemek için bu kodu Sihirbazı'nı kullanın. MFC desteği için Win32 projeleri MFC sınıfları de ekleyebilirsiniz. Projenizi oluşturduğunuzda, belirttiğiniz özellikler bu iletişim kutusunda seçeneklerini belirleyin.  
  
## <a name="names"></a>Adlar  
 Bu sayfada, sınıf adı, temel sınıf ve dosya adları için yeni sınıf belirtin.  
  
 **Sınıf adı**  
 Kimlikleri ve bu sayfadaki dosya adları için varsayılan taban sağlar ve yeni sınıfın adını belirtir. C++ sınıfları genellikle "C" ile başlangıç böylece Örneğin, "CMyClass" "MyClass.h" olur, vb.  
  
 **Taban sınıfı**  
 Yeni sınıfı temel sınıfın adını belirtir. Varsayılan olarak, temel sınıftır [CWnd](../../mfc/reference/cwnd-class.md). Seçtiğiniz temel sınıfı, bu sayfada diğer kutuları etkin olup olmadığını belirler.  
  
 Taban sınıfı sınıfı bir iletişim kimliği veya bir kaynak kimliği sahip olup olmadığını belirleyen ayarladığınız sınıfın türü Genel tür sınıfı aşağıdaki gibidir:  
  
-   Gibi sınıfları [CButton](../../mfc/reference/cbutton-class.md), [CWnd](../../mfc/reference/cwnd-class.md), veya [CDocument](../../mfc/reference/cdocument-class.md), bir iletişim kutusu gerektirmez kimliği veya kaynak kimliği Bu sınıfların bir iletişim kutusu veya kaynak kimliği kullanmayın Temel sınıfınız için bu sınıflarından birini seçerseniz **iletişim kimliği** kutusu ve **DHTML kaynak kimliği** kutusu soluk görünür.  
  
-   Gibi sınıfları [CDialog](../../mfc/reference/cdialog-class.md), [Cformview'yu](../../mfc/reference/cformview-class.md), veya [CPropertyPage](../../mfc/reference/cpropertypage-class.md), bir iletişim kimliği gerektirir  
  
-   Sınıf [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md), iletişim kimliği, DHTML kaynak kimliği ile bir HTML dosya adı gerektirir.  
  
 Bir iletişim kimliği gerektiren sınıfları için onu daha verimli kullanmak için bulabilirsiniz [Kaynak Düzenleyici](../../windows/resource-editors.md) Kimliğini, iletişim kaynağını oluşturma atamak [Özellikler penceresini](/visualstudio/ide/reference/properties-window)ve ilişkili bir sınıf oluşturun Bu kaynak kimliği ile Bkz: [yeni bir iletişim kutusu oluşturma](../../windows/creating-a-new-dialog-box.md) standart bir Windows iletişim kutusu oluşturma hakkında daha fazla bilgi için.  
  
> [!NOTE]
>  Bir iletişim kutusu kaynağı ilk oluşturun ve yeni sınıfından türetilen `CDHtmlDialog`, standart Windows silme **Tamam** ve **iptal** varsayılan iletişim kutusunda görüntülenen düğmeleri. Standart Windows iletişim kutusu içeren kendi DHTML form barındıran **Tamam** ve **iptal** düğmeler.  
  
 İletişim kutusu Windows denetimleri ve DHTML denetimleri içerebilir ancak önerilmez.  
  
 **İletişim kimliği**  
 Seçtiyseniz, iletişim Kimliğini belirtir `CDialog`, `CFormView`, `CPropertyPage`, veya `CDHtmlDialog` olarak **temel sınıfı**.  
  
 **.h dosyası**  
 Yeni nesne sınıfı için üstbilgi dosyası adını ayarlar. Varsayılan olarak, bu ad, sağladığınız adının dayanır **sınıf adı**. Dosya adı tercih ettiğiniz bir konuma kaydedin veya varolan bir dosyaya sınıf bildirimi eklemek için üç nokta düğmesini tıklatın. Varolan bir dosyanın seçerseniz, sihirbaz bunu seçili konuma dek tıklatın kaydedilmeyecektir **son** Sihirbazı'nda.  
  
 Sihirbaz, bir dosyanın üzerine değildir. ' I tıklattığınızda varolan bir dosyanın adını seçeneğini belirlerseniz **son**, sınıf bildirimi dosyasının içeriğini eklenmiş olup olmadığını belirtmek için Sihirbazı ister. Tıklatın **Evet** ; dosyayı eklemek için tıklatın **Hayır** sihirbaza geri dönmek ve başka bir dosya adı belirtin.  
  
 **.cpp dosyası**  
 Yeni nesne sınıfı için uygulama dosyasının adını ayarlar. Varsayılan olarak, bu ad, sağladığınız adının dayanır **sınıf adı**. Dosya adı seçiminizi konuma kaydetmek için üç nokta düğmesini tıklatın. Tıklattığınız kadar dosya seçili konuma kaydedilmez **son** Sihirbazı'nda.  
  
 Sihirbaz, bir dosyanın üzerine değildir. ' I tıklattığınızda varolan bir dosyanın adını seçeneğini belirlerseniz **son**, sınıf uygulamasını dosyasının içeriğini eklenmiş olup olmadığını belirtmek için Sihirbazı ister. Tıklatın **Evet** ; dosyayı eklemek için tıklatın **Hayır** sihirbaza geri dönmek ve başka bir dosya adı belirtin.  
  
 **Etkin Erişilebilirlik**  
 MFC'nin Etkin Erişilebilirlik çağırarak san'nin [EnableActiveAccessibility](../../mfc/reference/cwnd-class.md#enableactiveaccessibility) oluşturucuda. Türetilmiş sınıflar için bu seçenek kullanılabilir [CWnd](../../mfc/reference/cwnd-class.md).  
  
 **DHTML kaynak kimliği**  
 Türetilen sınıflara uygulanır `CDHtmlDialog` yalnızca. DHTML iletişim kutusu kaynak Kimliğini belirtir. Kaynak Kimliği HTML iletişim kutusu dosya adı ile birlikte projenin .rc dosyasının HTML bölümünde görüntülenir. Bu kimlik tarafından tanımlanan DHTML kaynak tarafından tanımlanan iletişim kutusu tarafından barındırılan **iletişim kimliği**.  
  
 **. HTM dosyası**  
 Türetilen sınıflara uygulanır `CDHtmlDialog` yalnızca. DHTML iletişim kutusu için HTML dosya adını ayarlar. Varsayılan olarak, bu dosya adı, sınıf adını temel alır. DHTML iletişim kutusu kaynak kimliği ile birlikte projenin .rc dosyasının HTML bölümünde dosya adı görünür  
  
 **Otomatikleştirme**  
 Destek için sınıf düzeyinde ayarlar [Otomasyon](../../mfc/automation.md). Sınıf düzeyinde Otomasyon Otomasyon destekleyen tüm sınıflar için kullanılabilir. Otomasyon desteği ile oluşturulan projeleri için de kullanılabilir. Diğer bir deyişle, ya da bir MFC projesine, [ATL destekleyen](../../atl/reference/mfc-support-in-atl-projects.md), veya kendisi için seçtiğiniz bir MFC projesine **Otomasyon** onay kutusuna [Gelişmiş Özellikler](../../mfc/reference/advanced-features-mfc-application-wizard.md) MFC sayfası Uygulama Sihirbazı.  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|**Yok**|Sınıf Otomasyonu desteği yok sahip olduğunu gösterir.|  
|**Otomatikleştirme**|Sınıf Otomasyonu desteklediğini belirtir. Bu seçeneği seçerseniz, yeni oluşturulan sınıf, Microsoft Visual Basic ve Microsoft Excel gibi Automation istemci uygulamaları tarafından programlanabilir nesnesi olarak kullanılabilir. Bu seçenek, bu tablodan sonra listelenen temel sınıflar için kullanılamaz.|  
|**Tür Kimliğine göre creatable**|Sınıf ve Proje Otomasyonu kullanarak bu sınıfın nesnelerini oluşturma başka uygulamaları desteklemeniz gösterir. Bu seçenek ile Otomasyon istemcileri doğrudan bir Otomasyon nesnesi oluşturabilirsiniz. Tür kimliği metin kutusunda istemci uygulaması tarafından oluşturulacak nesne belirtmek için kullanılır; Bu sistem çapında ve benzersiz olması gerekir. Bu seçenek, bu tablodan sonra listelenen temel sınıflar için kullanılamaz.|  
  
 Otomasyon desteği aşağıdaki temel sınıflar için kullanılabilir değil:  
  
-   `CAsyncMonitorFile`  
  
-   `CAsyncSocket`  
  
-   `CCachedDataPathProperty`  
  
-   `CConnectionPoint`  
  
-   `CDatabase`  
  
-   `CDataPathProperty`  
  
-   `CHttpFilter`  
  
-   `CHttpServer`  
  
-   `CInternetSession`  
  
-   `CObject`  
  
-   `CSocket`  
  
 **Tür kimliği**  
 Sınıf türü kimliği ayarlar. **Türü kimliği** kutusunu proje adı ve yeni sınıf adı şu şekilde sıralar: *MFCProj.MFCClass*. Bu kimliği yalnızca seçtiyseniz değiştirilebilir **Otomasyon** seçeneği **Creatable tür Kimliğine göre**.  
  
 **DocTemplate kaynak oluştur**  
 Uygulama tarafından oluşturulan belgeleri belge şablonu kaynaklara sahip olduğunu gösterir. Bu onay kutusunu etkinleştirmek için projeyi MFC belge/görünüm mimarisi desteklemesi gerekir ve bu sınıfın temel sınıf olmalıdır [Cformview'yu](../../mfc/reference/cformview-class.md).  
  
 Bkz: [belge şablonları ve belge/görünüm oluşturma işlemi](../../mfc/document-templates-and-the-document-view-creation-process.md) daha fazla bilgi için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC sınıfı](../../mfc/reference/adding-an-mfc-class.md)   
 [Sınıf ekleme](../../ide/adding-a-class-visual-cpp.md)
