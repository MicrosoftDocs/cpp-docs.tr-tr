---
title: Üye değişkeni Ekleme Sihirbazı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.codewiz.variable.overview
dev_langs:
- C++
helpviewer_keywords:
- Add Member Variable Wizard [C++]
ms.assetid: 73e8fa99-ac1a-42e2-8fc2-4684b9eb6d4d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4d4518a48d51e6187015dc3fd7b5456e04e1ae84
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45701538"
---
# <a name="add-member-variable-wizard"></a>Üye Değişkeni Ekleme Sihirbazı
Bu sihirbaz bir üye değişken bildiriminde üstbilgi dosyasına ekler ve seçeneklere bağlı olarak, bu kod için .cpp dosyası ekleyebilirsiniz. Sihirbazı kullanarak üye değişkenini ekledikten sonra kodu geliştirme ortamında düzenleyebilirsiniz.  
  
- **Erişim**

   Erişim bir üye değişkeni ayarlar. Erişim değiştiricileri bir üye değişkeni diğer sınıflara sahip erişimi belirtin sözcüklerdir. Bkz: [üye erişim denetimi](../cpp/member-access-control-cpp.md) erişim belirtme hakkında daha fazla bilgi için. Üye değişkeni erişim düzeyini ayarlamak **genel** varsayılan olarak.  
  
-   [public](../cpp/public-cpp.md)  
  
-   [protected](../cpp/protected-cpp.md)  
  
-   [private](../cpp/private-cpp.md)  
  
- **Değişken türü**

   Eklediğiniz üye değişkeni için dönüş türünü ayarlar.  
  
   - Bir iletişim kutusu denetimi olmayan bir üye değişkeni ekliyorsanız, kullanılabilir türler listesinden seçin.  
  
      Türleri hakkında daha fazla bilgi için bkz: [temel türler](../cpp/fundamental-types-cpp.md).  
  
      |||  
      |-|-|  
      |**char**|**short**|  
      |**double**|**İmzasız char**|  
      |**float**|**işaretsiz int**|  
      |**int**|**İmzasız long**|  
      |**long**||  
  
   - Bir iletişim kutusu denetimi için bir üye değişkeni ekliyorsanız, bu kutu bir denetim veya değer için döndürülen nesnenin türü ile doldurulur. Seçerseniz **denetimi**, ardından **değişken türü** seçtiğiniz denetim temel sınıfını belirtir **denetim kimliği** kutusu. İletişim kutusu denetiminin bir değer içerebilir ve seçerseniz **değer**, ardından **değişken türü** denetimi içerebileceği değeri uygun türünü belirtir. Bkz: [iletişim kutusu denetimleri ve değişken türleri](../ide/dialog-box-controls-and-variable-types.md) daha fazla bilgi için.  
  
      Bu değer seçime bağlıdır **denetim kimliği** ve değiştirilemez.  
  
- **Değişken adı**

   Eklediğiniz üye değişkeni adını ayarlar. Üye değişkenleri genellikle tanımlayıcı dizesi "sizin için varsayılan olarak sağlanan m_," ile başlar.  
  
- **Denetim değişkeni**

   Üye değişkeni içeren bir iletişim kutusu denetimine yönetir gösterir [veri değişimi ve veri doğrulama](../mfc/dialog-data-exchange-and-validation.md) destekler. Bkz: [DoDataExchange](../mfc/reference/cwnd-class.md#dodataexchange) daha fazla bilgi için. Bu seçenek yalnızca türetilen sınıfların eklenen üye değişkenleri için kullanılabilir [CDialog](../mfc/reference/cdialog-class.md). Etkinleştirmek için bu kutuyu seçin **denetim kimliği** ve **denetim türü** seçenekleri.  
  
- **Denetim Kimliği**

   Eklemekte olduğunuz denetim değişkeni için bir kimlik ayarlar. Listeden üye değişkeni ekleme denetim türü kimliği seçin. Yalnızca etkin olduğunda listesidir **denetim değişkeni** kutusu seçilidir ve zaten iletişim kutusuna eklenen denetimler için kimlikleri için sınırlı. Örneğin, standart için **Tamam** düğme denetimi kimliğidir **IDOK**.  
  
   |Seçenek|Açıklama|  
   |------------|-----------------|  
   |**Denetimi**|Bu seçenek, Denetim türü için varsayılan olarak ayarlanır. Denetim kendisini ve durumu ya da değil içeriği (liste kutusu, birleşik giriş kutusu veya düzenleme kutusu yapmak isteyebileceğiniz gibi) yönettiği denetimi.|  
   |**Değer**|(Örneğin, bir düzenleme kutusuna) bir değer içermesi veya yansıtacak bir durumda (örneğin, bir onay kutusu) denetim tipleri için ve kendisi için bu seçenek kullanılabilir aralık, içeriği veya durum yönettiğiniz. Bkz: [iletişim kutusu denetimleri ve değişken türleri](../ide/dialog-box-controls-and-variable-types.md) daha fazla bilgi için.|  
  
- **Kategori**

   Değişkeni bir denetim türü veya denetimin değerini temel alan olup olmadığını belirtir.  
  
- **Denetim türü**

   Eklenen denetimin türünü ayarlar. Bu kutuyu değiştirmek kullanılabilir değil. Örneğin, bir düğme denetim türü olan **düğmesi**, ve bir birleşik giriş kutusu denetim türünü **COMBOBOX**. Bkz: [iletişim kutusu denetimleri ve değişken türleri](../ide/dialog-box-controls-and-variable-types.md) daha fazla bilgi için.  
  
- **En fazla karakter**

   Yalnızca **değişken türü** ayarlanır [CString](../atl-mfc-shared/reference/cstringt-class.md). En fazla denetimi içerebileceği karakter sayısını belirtir.  
  
- **En düşük değer**

   Değişken türü olduğunda kullanılabilir **BOOL**, `int`, **UINT**, **uzun**, `DWORD`, **float**, **çift**, **bayt**, **kısa**, [COLECurrency](../mfc/reference/colecurrency-class.md) veya [CTime](../atl-mfc-shared/reference/ctime-class.md). Bir ölçek veya tarih aralığını kabul edilebilir en düşük değeri gösterir.  
  
- **En yüksek değer**

   Değişken türü olduğunda kullanılabilir **BOOL**, `int`, **UINT**, **uzun**, `DWORD`, **float**, **çift**, **bayt**, **kısa**, `COLECurrency` veya `CTime`. Bir ölçek veya tarih aralığını kabul edilebilir en yüksek değeri gösterir.  
  
- **.h dosyası**

   ActiveX denetimleri için üye değişkenleri olan bir sarmalayıcı sınıfı gerektirir. Sınıf bildirimi eklemek için üst bilgi dosyası adını ayarlar.  
  
- **.cpp dosyası**

   ActiveX denetimleri için üye değişkenleri olan bir sarmalayıcı sınıfı gerektirir. Sınıf tanımı eklemek için uygulama dosyasının adını ayarlar.  
  
- **Yorum**

   Üye değişkeni için üst bilgi dosyası bir açıklama sağlar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Üye değişkeni ekleme](../ide/adding-a-member-variable-visual-cpp.md)