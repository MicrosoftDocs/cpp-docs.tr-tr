---
title: 'Özel durumlar: Kendi İşlevlerinizden özel durumları atma | Microsoft Docs'
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
ms.openlocfilehash: a6ef86f54442031b4383e6a0b8cc6f57e4e53d58
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46418430"
---
# <a name="exceptions-throwing-exceptions-from-your-own-functions"></a>Özel Durumlar: Kendi İşlevlerinizden Özel Durum Atma

Yalnızca MFC veya diğer kitaplıkları olarak işlevleri tarafından gönderilen özel durumları yakalamasını MFC özel durum işleme paradigma kullanmak mümkündür. Özel durumları olarak sınırlamasıyla işlevleri yazıyorsanız kitaplık kodu tarafından oluşturulan özel durumları yakalama ek olarak, özel durumlar kendi kodunuza oluşturabilecek.

Bir özel durum oluştuğunda yürütme geçerli işlevin durdurulur ve doğrudan atlar **catch** en içteki özel durum çerçevenin blok. Özel durum mekanizması, normal bir çıkış yolu bir işlevden atlar. Bu nedenle normal bir çıkış silineceğini bu bellek blokları silmek istediğinizden emin olmalıdır.

#### <a name="to-throw-an-exception"></a>Bir özel durum oluşturmak için

1. MFC yardımcı işlevleri gibi birini `AfxThrowMemoryException`. Bu işlevler, uygun türde bir ön tahsis özel durum nesnesi atar.

     Aşağıdaki örnekte, bir işlev, iki bellek blokları ayırmaya çalışır ve her iki ayırma başarısız olursa bir özel durum oluşturur:

     [!code-cpp[NVC_MFCExceptions#17](../mfc/codesnippet/cpp/exceptions-throwing-exceptions-from-your-own-functions_1.cpp)]

     İlk ayırma başarısız olursa, yetersiz bellek özel durum yeterlidir. İlk ayırma başarılı olur ancak ikincisi başarısız olursa, özel durum atmadan önce ilk ayırma öbeğini serbest gerekir. Her iki ayırma başarılı olursa, normal şekilde devam etmek ve işlev çıkarken blokları serbest.

     - veya -

1. Kullanıcı tanımlı bir özel durum bir sorun koşulu belirtmek için kullanın. Tüm bir sınıf bile, her tür bir öğe, özel durum oluşturabilecek.

     Aşağıdaki örnek, wave aygıttan Çıkart dener ve bir hata varsa, bir özel durum oluşturur.

     [!code-cpp[NVC_MFCExceptions#18](../mfc/codesnippet/cpp/exceptions-throwing-exceptions-from-your-own-functions_2.cpp)]

> [!NOTE]
>  MFC'nin varsayılan özel durumların işlenmesiyle uygulandığı yalnızca işaretçiler `CException` nesneleri (ve nesnelerin `CException`-türetilmiş sınıflar). Yukarıdaki örnekte, özel durum mekanizması MFC'nin atlar.

## <a name="see-also"></a>Ayrıca Bkz.

[Özel Durum İşleme](../mfc/exception-handling-in-mfc.md)

