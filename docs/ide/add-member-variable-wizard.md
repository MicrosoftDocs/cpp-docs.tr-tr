---
title: "Üye değişkeni Ekleme Sihirbazı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.codewiz.variable.overview
dev_langs:
- C++
helpviewer_keywords:
- Add Member Variable Wizard [C++]
ms.assetid: 73e8fa99-ac1a-42e2-8fc2-4684b9eb6d4d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b909ec7ccd830e088df81ca0b2db8cda133c7a20
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="add-member-variable-wizard"></a>Üye Değişkeni Ekleme Sihirbazı
Bu sihirbaz bir üye değişken bildirimi üstbilgi dosyası ekler ve belirlediğiniz seçeneklere bağlı olarak bu kodu .cpp dosyasına ekleyebilirsiniz. Sihirbazı'nı kullanarak üye değişkeni ekledikten sonra geliştirme ortamı kodda düzenleyebilirsiniz.  
  
 **Erişim**  
 Erişim için üye değişkeni ayarlar. Erişim değiştiricileri üye değişkeni diğer sınıflara sahip oldukları erişim belirttiğiniz anahtar sözcükler. Bkz: [üye erişim denetimi](../cpp/member-access-control-cpp.md) erişim belirtme hakkında daha fazla bilgi için. Üye değişkeni erişim düzeyini ayarlamak **ortak** varsayılan olarak.  
  
-   [public](../cpp/public-cpp.md)  
  
-   [protected](../cpp/protected-cpp.md)  
  
-   [private](../cpp/private-cpp.md)  
  
 **Değişken türü**  
 Eklediğiniz üye değişkeni için dönüş türünü ayarlar.  
  
-   Bir iletişim kutusu denetimi değil bir üye değişkenine ekliyorsanız, kullanılabilir türler listesinden seçin.  
  
     Türleri hakkında daha fazla bilgi için bkz: [temel türleri](../cpp/fundamental-types-cpp.md).  
  
    |||  
    |-|-|  
    |`char`|**short**|  
    |**double**|`unsigned char`|  
    |**float**|`unsigned int`|  
    |`int`|`unsigned long`|  
    |**long**||  
  
-   Bir iletişim kutusu denetimi için bir üye değişkeni ekliyorsanız, bu kutu bir denetim veya değer için döndürülen nesne türü ile doldurulur. Seçerseniz **denetim**, ardından **değişken türü** öğesinde denetim temel sınıfını belirtir **denetim kimliği** kutusu. İletişim kutusu denetimi bir değer içeriyorsa ve seçerseniz **değeri**, ardından **değişken türü** denetim içerebilir değer uygun türünü belirtir. Bkz: [iletişim kutusu denetimleri ve değişken türleri](../ide/dialog-box-controls-and-variable-types.md) daha fazla bilgi için.  
  
     Bu değer seçime bağlıdır **denetim kimliği** ve değiştirilemez.  
  
 **Değişken adı**  
 Eklediğiniz üye değişkeni adını ayarlar. Üye değişkenleri genellikle tanımlayıcı dizesi "sizin için varsayılan olarak sağlanan m_," ile başlar.  
  
 **Denetim değişkeni**  
 Üye değişkeni içeren bir iletişim kutusu denetimine yönetir gösterir [veri değişimi ve veri doğrulama](../mfc/dialog-data-exchange-and-validation.md) destekler. Bkz: [DoDataExchange](../mfc/reference/cwnd-class.md#dodataexchange) daha fazla bilgi için. Bu seçenek yalnızca türetilmiş sınıflara eklenen üye değişkenleri için kullanılabilir [CDialog](../mfc/reference/cdialog-class.md). Etkinleştirmek için bu kutuyu işaretleyin **denetim kimliği** ve **denetim türü** seçenekleri.  
  
 **Denetim Kimliği**  
 Eklediğiniz denetim değişkeni Kimliğini ayarlar. Üye değişkeni ekleme denetim türü için kimliği listeden seçin. Yalnızca etkin olduğunda listesidir **denetim değişkeni** kutusu seçilidir ve iletişim kutusu zaten eklenmiş denetimleri için kimlikleri için sınırlı olur. Örneğin, standart **Tamam** düğme denetim kimliğidir **IDOK**.  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|**Denetimi**|Bu seçenek, Denetim türü için varsayılan olarak ayarlanır. (Liste kutusu, birleşik giriş kutusu veya düzenleme kutusu yapmak istediğiniz gibi) kendisi ve değil durumu veya içeriği denetimi yönettiği denetimi.|  
|**Değer**|Kendisi için ve (örneğin, bir düzenleme kutusu) bir değer içeren veya durumu (örneğin, bir onay kutusu) yansıtacak denetim türleri için bu seçeneği kullanılabilir aralığı, içeriği veya durum yönetmek. Bkz: [iletişim kutusu denetimleri ve değişken türleri](../ide/dialog-box-controls-and-variable-types.md) daha fazla bilgi için.|  
  
 **Kategori**  
 Değişkeni denetim türü veya denetiminin değerine göre belirtir.  
  
 **Denetim türü**  
 Eklenmekte olan denetim türünü ayarlar. Bu kutu değiştirmek kullanılabilir değil. Örneğin, bir düğme denetim türü olan **düğmesini**, ve birleşik giriş kutusu denetim türü **COMBOBOX**. Bkz: [iletişim kutusu denetimleri ve değişken türleri](../ide/dialog-box-controls-and-variable-types.md) daha fazla bilgi için.  
  
 **En fazla karakter**  
 Yalnızca **değişken türü** ayarlanır [CString](../atl-mfc-shared/reference/cstringt-class.md). En fazla denetim tutabilir karakter sayısını belirtir.  
  
 **En küçük değer**  
 Yalnızca değişken türü olduğunda kullanılabilir **BOOL**, `int`, **UINT**, **uzun**, `DWORD`, **float**, **çift**, **bayt**, **kısa**, [COLECurrency](../mfc/reference/colecurrency-class.md) veya [CTime](../atl-mfc-shared/reference/ctime-class.md). Bir ölçek veya tarih aralığı için kabul edilebilir en düşük değer gösterir.  
  
 **En yüksek değeri**  
 Yalnızca değişken türü olduğunda kullanılabilir **BOOL**, `int`, **UINT**, **uzun**, `DWORD`, **float**, **çift**, **bayt**, **kısa**, `COLECurrency` veya `CTime`. Bir ölçek veya tarih aralığı için kabul edilebilir en yüksek değeri gösterir.  
  
 **.h dosyası**  
 ActiveX denetimleri için sarmalayıcı sınıfı, üye değişkenleri gerektirir. Sınıf bildirimi eklemek için üstbilgi dosyası adını ayarlar.  
  
 **.cpp dosyası**  
 ActiveX denetimleri için sarmalayıcı sınıfı, üye değişkenleri gerektirir. Sınıf tanımı eklemek için uygulama dosyasının adını ayarlar.  
  
 **Yorum**  
 Üstbilgi dosyasında üye değişkeni için bir açıklama sağlar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Üye değişkeni ekleme](../ide/adding-a-member-variable-visual-cpp.md)