---
title: 'Özel Durumlar: Kendi İşlevlerinizden Özel Durum Atma'
ms.date: 11/04/2016
helpviewer_keywords:
- throwing exceptions [MFC], from functions
- functions [MFC], throwing exceptions
- exceptions [MFC], throwing
ms.assetid: 492976e8-8804-4234-8e8f-30dffd0501be
ms.openlocfilehash: 6484594df7636fd52ac46ab1cc212c8e2ec0278e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81359283"
---
# <a name="exceptions-throwing-exceptions-from-your-own-functions"></a>Özel Durumlar: Kendi İşlevlerinizden Özel Durum Atma

MFC özel durum işleme paradigmasını yalnızca MFC veya diğer kitaplıklarda işlevler tarafından atılan özel durumları yakalamak için kullanmak mümkündür. Kitaplık kodu tarafından atılan özel durumları yakalamaya ek olarak, olağanüstü koşullarla karşılaşabilecek işlevler yazıyorsanız, kendi kodunuzdan özel durumlar atabilirsiniz.

Bir özel durum atıldığında, geçerli işlevin yürütülmesi durdurulur ve doğrudan en içteki özel durum çerçevesinin **catch** bloğuna atlar. Özel durum mekanizması, normal çıkış yolunu bir işlevden atlar. Bu nedenle, normal bir çıkışta silinecek bellek bloklarını sildiğimden emin olmalısınız.

#### <a name="to-throw-an-exception"></a>Bir özel durum atmak için

1. MFC yardımcı işlevlerinden birini kullanın, `AfxThrowMemoryException`örneğin. Bu işlevler, uygun türde önceden ayrılmış bir özel durum nesnesi atar.

   Aşağıdaki örnekte, bir işlev iki bellek bloğu ayırmaya çalışır ve her iki ayırma başarısız olursa bir özel durum atar:

   [!code-cpp[NVC_MFCExceptions#17](../mfc/codesnippet/cpp/exceptions-throwing-exceptions-from-your-own-functions_1.cpp)]

   İlk ayırma başarısız olursa, bellek özel durum atabilirsiniz. İlk ayırma başarılı olursa, ancak ikincisi başarısız olursa, özel durumu atmadan önce ilk ayırma bloğunu serbest kaldırmanız gerekir. Her iki ayırma da başarılı olursa, normal bir şekilde ilerleyebilir ve işlevden çıkarken blokları serbest kalabilirsiniz.

     - veya -

1. Sorun durumunu belirtmek için kullanıcı tanımlı bir özel durum kullanın. Herhangi bir türden bir öğeyi, hatta tüm bir sınıfı özel durum olarak atabilirsiniz.

   Aşağıdaki örnek, bir dalga aygıtı üzerinden bir ses çalmaya çalışır ve bir hata varsa bir özel durum atar.

   [!code-cpp[NVC_MFCExceptions#18](../mfc/codesnippet/cpp/exceptions-throwing-exceptions-from-your-own-functions_2.cpp)]

> [!NOTE]
> MFC'nin varsayılan özel durum işlemesi yalnızca `CException` nesnelere (ve `CException`türetilmiş sınıfların nesneleri) işaretçilere uygulanır. Yukarıdaki örnek, MFC'nin özel durum mekanizmasını atlar.

## <a name="see-also"></a>Ayrıca bkz.

[Özel Durum İşleme](../mfc/exception-handling-in-mfc.md)
