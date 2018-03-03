---
title: "TN023: Standart MFC kaynakları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.resources
dev_langs:
- C++
helpviewer_keywords:
- resources [MFC]
- TN023
- standard resources
ms.assetid: 60af8415-c576-4c2f-a711-ca5da0b9a1f2
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6fded011fda52dfde46804b03699dc93469e5e32
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="tn023-standard-mfc-resources"></a>TN023: Standart MFC Kaynakları
Bu not ile sağlanan ve MFC Kitaplığı tarafından gerekli standart kaynaklar açıklanır.  
  
## <a name="standard-resources"></a>Standart kaynaklar  
 MFC uygulamanızda kullanabileceğiniz önceden tanımlanmış kaynak iki kategorileri sunar: küçük resimler kaynaklar ve standart çerçevesi kaynakları.  
  
 Küçük resim, framework bağlı değil ancak uygulamanızın kullanıcı arabirimi eklemek istediğiniz ek kaynaklara kaynaklardır. MFC genel örnek aşağıdaki küçük resimler kaynaklar içerdiği [küçük](../visual-cpp-samples.md):  
  
-   Common.rc: Tek bir içeren dosya kaynakların:  
  
    -   Çeşitli iş ve veri işleme görevlerini temsil eden simgeleri büyük bir koleksiyonu.  
  
    -   Birçok ortak İmleçler (Ayrıca bkz. Afxres.rc).  
  
    -   Birkaç araç çubuğu düğmelerini içeren bir araç bitmap.  
  
    -   Commdlg.dll tarafından kullanılan bit eşlem ve simge kaynaklar.  
  
-   Indicate.rc: Caps Lock "CAP" gibi durum çubuğu anahtar Durum göstergeleri için dize kaynaklarını içerir.  
  
-   Prompts.rc: için "Yeni belge oluştur" gibi önceden tanımlanmış her komut istemi menü dize kaynaklarını içeren `ID_FILE_NEW`.  
  
-   COMMDLG.rc: standart COMMDLG iletişim kutusu şablonları içeren bir Visual C++ uyumlu .rc dosyası.  
  
 Standart framework kaynaklar için iç uygulamaları framework bağlıdır AFX tanımlı kimlikleri kaynaklardır. Nadiren bu AFX tanımlı kaynakları değiştirmeniz gerekecektir. Bunu yaparsanız, bu konunun ilerleyen bölümlerinde açıklanan yordamı izlemelisiniz.  
  
 Aşağıdaki çerçevesi kaynakları MFC\INCLUDE dizininde yer almaktadır:  
  
-   Afxres.rc: ortak kaynakları framework tarafından kullanıldı.  
  
-   Afxprint.rc: Kaynakları yazdırmaya özel.  
  
-   Afxolecl.rc: OLE istemci uygulamaları için belirli kaynaklar.  
  
-   Afxolev.rc: Tam OLE sunucu uygulamaları için belirli kaynaklar.  
  
## <a name="using-clip-art-resources"></a>Küçük resim kaynaklarını kullanma  
  
#### <a name="to-use-a-clip-art-binary-resource"></a>Bir küçük resim ikili kaynak kullanmak için  
  
1.  Visual c++'ta, uygulamanızın kaynak dosyasını açın.  
  
2.  Common.rc açın. Bu dosya, tüm ikili küçük resimler kaynaklar içeriyor. Derlenmiş Common.rc dosyası bu biraz zaman alabilir.  
  
3.  CTRL tuşunu basılı tutarak, uygulamanızın kaynak dosyasına Common.rc kullanmak istediğiniz kaynakları sürükleyin.  
  
 Diğer küçük resim kaynakları kullanmak için aynı adımları izleyin. Tek fark, Common.rc yerine uygun .rc dosyayı açacak ' dir.  
  
> [!NOTE]
>  Yanlışlıkla Common.rc dışında kaynaklar kalıcı olarak taşıyamazsınız dikkat edin. CTRL tuşunu basılı tutarak kaynakları sürükleyin, bir kopyasını oluşturur. Basılı tutarak sürükleyin, CTRL değil, kaynakları taşınır. Yanlışlıkla değişiklikleri Common.rc dosyasına yaptığınız endişeniz varsa, değişiklikler için Common.rc kaydedilip kaydedilmeyeceğini sorulduğunda "Hayır"'i tıklatın.  
  
> [!NOTE]
>  Özel bir .rc Kaynak dosyalarınız `TEXTINCLUDE` yanlışlıkla standart .rc dosyaları üstünde kaydetmesini engeller kaynak bunlara.  
  
### <a name="customizing-standard-framework-resources"></a>Standart çerçevesi kaynakları özelleştirme  
 Standart çerçevesi kaynakları genellikle yer alan bir uygulamada kullanarak # komutu bir uygulamanın kaynak dosyasında include. AppWizard kaynak dosyası oluşturur. Bu dosyayı seçtiğiniz bağlı olarak hangi AppWizard seçenekleri uygun standart çerçevesi kaynakları içerir. Gözden geçirin, ekleyin veya derleme zamanı yönergeleri değiştirerek hangi kaynaklar dahil kaldırın. Bunu yapmak için açın **kaynak** menü ve select **kümesi içeren**. "Derleme zamanı yönergeleri" bakma öğesi düzenleyin. Örneğin:  
  
```  
#include "afxres.rc"  
#include "afxprint.rc"  
```  
  
 Standart çerçevesi kaynakları özelleştirme en yaygın durumda ekleme veya ek kaldırma içeren yazdırmak için OLE istemci ve OLE sunucu desteği.  
  
 Belirli uygulamanız için standart çerçevesi kaynakları içerikleri özelleştirmek isteyebilirsiniz bazı nadir durumlarda yalnızca ekleyin ve dosyanın tamamını kaldırın. Aşağıdakilere adımları dahil olan kaynakları nasıl sınırlayabilirsiniz göster:  
  
##### <a name="to-customize-the-contents-of-a-standard-resource-file"></a>Standart kaynak dosyasının içeriğini özelleştirmek için  
  
1.  Visual C++'da kaynak dosyasını açın.  
  
2.  Kaynak kümesi içeren komutunu kullanarak kaldırma `#include` özelleştirmek istediğiniz standart .rc dosyası için. Örneğin, Baskı Önizleme araç özelleştirmek için kaldırmak `#include "afxprint.rc"` satır.  
  
3.  Uygun standart kaynakları dosyaları MFC\INCLUDE içinde açın. Örnekte bu konunun önceki kısımlarında uygun MFC\Include\Aafxprint.rc dosyasıdır  
  
4.  Tüm kaynakları standart .rc dosyasından uygulama kaynak dosyasına kopyalayın.  
  
5.  Uygulama kaynak dosyanızdaki standart kaynakları kopyasını değiştirin.  
  
> [!NOTE]
>  Standart .rc dosyaları kaynaklarında doğrudan değiştirmeyin. Bunun yapılması her uygulama, yalnızca üzerinde çalıştıkları bir kullanılabilir kaynakları değiştirecektir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sayıya göre teknik notlar](../mfc/technical-notes-by-number.md)   
 [Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)

