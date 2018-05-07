---
title: 'Özel durumlar: Kendi İşlevlerinizden özel durum atma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- throwing exceptions [MFC], from functions
- functions [MFC], throwing exceptions
- exceptions [MFC], throwing
ms.assetid: 492976e8-8804-4234-8e8f-30dffd0501be
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dae6f2c0d1cab021cc91854a34f10423a1122dec
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="exceptions-throwing-exceptions-from-your-own-functions"></a>Özel Durumlar: Kendi İşlevlerinizden Özel Durum Atma
MFC özel durum işleme standardı yalnızca MFC ya da diğer kitaplıkları işlevlerde tarafından oluşturulan özel durumları yakalamak için kullanmak mümkündür. Özel durumları karşılaşabilirsiniz işlevleri yazıyorsanız kitaplık kodu tarafından oluşturulan özel durumları yakalama ek olarak, özel durumlar kendi kodunuzdan atabilirsiniz.  
  
 Bir özel durum, geçerli işlevi yürütülmesi durdurulur ve doğrudan atlar **catch** en içteki özel durum çerçeve bloğu. Özel durum mekanizması normal çıkış yolu bir işlevden atlar. Bu nedenle, normal Çık'silinecek bu bellek blokları silmek istediğinizden emin olmalıdır.  
  
#### <a name="to-throw-an-exception"></a>Bir özel durum için  
  
1.  MFC yardımcı işlevleri birini gibi kullandığınız `AfxThrowMemoryException`. Bu işlevler uygun türde bir ön tahsis özel durum nesnesi atar.  
  
     Aşağıdaki örnekte, bir işlev iki bellek blok ayırmaya çalışır ve her iki ayırma başarısız olursa bir özel durum oluşturur:  
  
     [!code-cpp[NVC_MFCExceptions#17](../mfc/codesnippet/cpp/exceptions-throwing-exceptions-from-your-own-functions_1.cpp)]  
  
     İlk ayırma başarısız olursa, yalnızca bellek özel durum. İlk ayırma başarılı olur ancak ikinci başarısız olursa, özel durum atma önce ilk ayırma bloğu boş olmalıdır. Her iki ayırma başarılı olursa, normal olarak devam etmek ve blokları işlevi çıkarken boş.  
  
     - veya -  
  
2.  Kullanıcı tanımlı bir özel durum bir sorun koşulu belirtmek için kullanın. Tüm bir sınıf bile, tüm türünde bir öğe, özel durum.  
  
     Aşağıdaki örnek, sesi wave cihazı üzerinden çalışır ve bir hata olduğunda bir özel durum oluşturur.  
  
     [!code-cpp[NVC_MFCExceptions#18](../mfc/codesnippet/cpp/exceptions-throwing-exceptions-from-your-own-functions_2.cpp)]  
  
> [!NOTE]
>  MFC'nin varsayılan işleme özel durumlar geçerlidir yalnızca işaretçileri `CException` nesneleri (ve nesnelerin `CException`-türetilmiş sınıfları). Yukarıdaki örnekte MFC'nin özel durum mekanizması atlar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özel Durum İşleme](../mfc/exception-handling-in-mfc.md)

