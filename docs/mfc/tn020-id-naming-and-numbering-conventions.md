---
title: "TN020: Kimlik adlandırma ve numaralandırma kuralları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.id
dev_langs: C++
helpviewer_keywords:
- TN020
- resource identifiers, naming and numbering
- resource identifiers
ms.assetid: aecbd2cf-68b3-47f6-ae21-b1f507917245
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a666c2183276b95a9405400de8acc0117c7134e1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="tn020-id-naming-and-numbering-conventions"></a>TN020: Kimlik Adlandırma ve Numaralandırma Kuralları
Bu Not kimlik adlandırma ve kaynakları, komutları, dizeleri, denetimleri ve alt windows için MFC 2.0 kullanan numaralandırma kuralları açıklar.  
  
 MFC kimlik adlandırma ve numaralandırma kuralları aşağıdaki gereksinimleri karşılamak üzere tasarlanmıştır:  
  
-   MFC Kitaplığı ve Visual C++ kaynak Düzenleyicisi tarafından desteklenen MFC uygulamaları genelinde kullanılan tutarlı bir kimliği adlandırma standart sağlar. Bu türü ve kimliğini bir kaynaktan kökeni yorumlamak Programcı kolaylaştırır  
  
-   Belirli türde bir kimlikleri arasında güçlü 1-1 ilişki vurgulayın.  
  
-   Windows kimlikleri adlandırma zaten yaygın olarak kullanılan standartlarına uygun.  
  
-   Bölüm kimliği numaralandırma alanı. Kimlik numaraları Programcı, MFC, Windows ve Visual C++ düzenlenebilir kaynaklar tarafından atanabilir. Uygun bölümleme kimlik numaraları yinelenmesini önlenmesine yardımcı olur.  
  
## <a name="the-id-prefix-naming-convention"></a>Kimlik öneki adlandırma kuralı  
 Çeşitli türlerde kimlikleri bir uygulamada ortaya çıkabilir. MFC kimliği adlandırma kuralı farklı önekleri farklı kaynak türleri için tanımlar.  
  
 MFC önek "IDR_" birden çok kaynak türü için geçerli bir kaynak kimliği göstermek için kullanır. Örneğin, belirli çerçeve penceresi için bir menü, Hızlandırıcı, dize ve simge kaynak belirtmek için "IDR_" ön eki aynı MFC kullanır. Aşağıdaki tabloda, çeşitli ön ekleri ve bunların kullanım gösterilmektedir:  
  
|önek|Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında|  
|------------|---------|  
|IDR_|(Öncelikle menüleri, hızlandırıcıları ve Şerit için kullanılır) birden çok kaynak türü için.|  
|IDD_|İletişim şablonu için kaynaklar (örneğin, IDD_DIALOG1).|  
|IDC_|İmleç kaynakları için.|  
|IDI_|Simge kaynaklar için.|  
|IDB_|Bit eşlem kaynaklar için.|  
|IDS_|Dize kaynakları için.|  
  
 Bir iletişim kutusu kaynağı içinde MFC bu kuralları aşağıdaki gibidir:  
  
|Ön eki veya etiketi|Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında|  
|---------------------|---------|  
|IDOK, IDCANCEL|Standart düğme için kimlikleri.|  
|IDC_|Diğer iletişim kutusu denetimleri için.|  
  
 "IDC_" öneki imleçler için de kullanılır. Tipik bir uygulama birkaç imleçler ve birçok iletişim kutusu denetimleri olduğundan bu ad çakışması genellikle bir sorun değildir.  
  
 Menü kaynağı içinde MFC bu kuralları aşağıdaki gibidir:  
  
|önek|Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında|  
|------------|---------|  
|IDM_|Menü öğeleri için MFC komutu mimarisi kullanmayın.|  
|ID_|MFC kullanan menü komutlarını mimarisi komutu.|  
  
 MFC komutu mimarisi izleyin komutları olmalıdır bir `ON_COMMAND` komut işleyici ve olabilir bir `ON_UPDATE_COMMAND_UI` işleyicisi. Bu komut işleyicileri MFC komutu mimarisi izlerseniz, bunlar düzgün menü komutu, bir araç çubuğu düğmesini veya bir iletişim çubuğu düğmesi için bağlı olan çalışmayacaktır. Aynı "ID_" öneki programın ileti çubuğu'nda görüntülenen menü istem dizesi için de kullanılır. Menü öğeleri, uygulamanızda çoğunu MFC komut kuralları izlemelidir. Tüm standart komut kimlikleri (örneğin, `ID_FILE_NEW`) Bu kuralı izleyin.  
  
 MFC "IDP_" ("IDS_") yerine dizeleri özel biçimi olarak da kullanır. İstemleri, diğer bir deyişle, ileti kutularında kullanılan dizeleri dizelerdir "IDP_" ön ekine sahip. "IDP_" dizeleri, program tarafından belirlenen dizeleri yer tutucu olarak "%1" ve "%2" içerebilir. "IDP_" dizeleri genellikle Yardım konuları ilişkili olan ve "IDS_" dizeleri yapın. "IDP_" dizeleri her zaman yerelleştirilir ve "IDS_" dizeleri yerelleştirilmemiş.  
  
 MFC kitaplığını "IDW_" önekini Denetim kimliklerinin (yerine "IDC_") özel biçimi olarak da kullanır. Bu kimlikleri görünümleri ve ayırıcılar gibi alt öğe pencerelerini framework sınıfları tarafından atanmış. MFC Uygulama kimlikleri "İle AFX_" öneki alır.  
  
## <a name="the-id-numbering-convention"></a>Kimliği numaralandırma kuralı  
 Aşağıdaki tabloda, belirli türlerine kimlikleri için geçerli aralıklar listeler. Teknik uygulamadan sınırları sınırlarının bazılarıdır ve diğerleri Windows önceden tanımlanmış kimlikler veya MFC ile varsayılan uygulamaları yazılımlarla çakışma kimliklerinizi önlemek üzere tasarlanmış kurallardır.  
  
 Önerilen aralıkları içindeki tüm kimliklerini tanımladığınız öneririz. 0 kullanılmadığından Bu aralıklar, alt sınır 1'dir. Genel kural kullanın ve 100 veya 101 ilk kimlik olarak kullanmak öneririz  
  
|önek|Kaynak türü|Geçerli aralık|  
|------------|-------------------|-----------------|  
|IDR_|birden çok|1 ile 0x6FFF|  
|IDD_|iletişim kutusu şablonları|1 ile 0x6FFF|  
|IDC_, IDI_, IDB_|imleçler, simgeler, bit eşlemler|1 ile 0x6FFF|  
|IDS_, IDP_|Genel dizeleri|1 ile 0x7FFF|  
|ID_|komutlar|0x8000 0xDFFF aracılığıyla|  
|IDC_|denetimler|8 0xDFFF ile|  
  
 Bu aralığı sınırları nedenleri:  
  
-   Kurala göre 0 kimlik değeri kullanılmaz.  
  
-   Windows uygulaması sınırlamaları doğru kaynak kimlikleri 0x7FFF eşit veya daha az olacak şekilde kısıtlayın.  
  
-   MFC'nin iç framework Bu aralıklar ayırır:  
  
    -   0x7FFF aracılığıyla 0x7000 (afxres.h bakın)  
  
    -   0xEFFF aracılığıyla 0xE000 (afxres.h bakın)  
  
    -   18000 (afxribbonres.h bakın) aracılığıyla 16000  
  
     Bu aralıklar, gelecekte MFC uygulamalarında değişebilir.  
  
-   Çeşitli Windows sistem komutlarını 0xFFFF aracılığıyla 0xF000 aralığı kullanın.  
  
-   1 ile 7 arasındaki denetim kimliklerini IDOK ve IDCANCEL gibi standart denetimler için ayrılmıştır.  
  
-   Dizeler için 0xFFFF aracılığıyla 0x8000 aralığını komutları için menü ister için ayrılmıştır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sayıya göre teknik notlar](../mfc/technical-notes-by-number.md)   
 [Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)

