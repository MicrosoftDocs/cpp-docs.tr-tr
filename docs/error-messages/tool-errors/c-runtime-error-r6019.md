---
description: 'Daha fazla bilgi edinin: C çalışma zamanı hatası R6019'
title: C Çalışma Zamanı Hatası R6019
ms.date: 11/04/2016
f1_keywords:
- R6019
helpviewer_keywords:
- R6019
ms.assetid: 8129923e-7db2-40ee-9602-def9365f8d28
ms.openlocfilehash: 190b836d5c0823b3644e4ff49812b5de05f421e8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97237640"
---
# <a name="c-runtime-error-r6019"></a>C Çalışma Zamanı Hatası R6019

Konsol cihazı açılamıyor

> [!NOTE]
> Bir uygulamayı çalıştırırken bu hata iletisiyle karşılaşırsanız, uygulama konsola erişmeye çalıştığı için kapatıldı, ancak yeterli izni yoktu. Bu hatanın birkaç olası nedeni vardır, ancak genellikle programın yönetici olarak çalıştırılması veya programda bir hata olması gerekir.
>
> Bu hatayı düzeltmek için aşağıdaki adımları deneyebilirsiniz:
>
> - Programı yönetici olarak çalıştırın.
> - Programı onarmak ya da yeniden yüklemek için **Denetim Masası** 'ndaki **uygulamalar ve Özellikler** veya **Programlar ve Özellikler** sayfasını kullanın.
> - Yazılım güncelleştirmeleri için **Denetim Masası** 'ndaki **Windows Update** kontrol edin.
> - Uygulamanın güncelleştirilmiş bir sürümünü denetleyin. Sorun devam ederse uygulama satıcısına başvurun.

**Programcılar için bilgiler**

Bu hata, uygulamanın konsol işlevi olarak adlandırılmasından, ancak işletim sisteminin konsola erişim izni vermediği için oluşur. Hata ayıklama modu dışında, Microsoft Store uygulamalarında konsol işlevlerine genellikle izin verilmez. Uygulamanızın çalışması için yönetici ayrıcalıkları gerekiyorsa, varsayılan olarak yönetici olarak çalışacak şekilde yüklendiğinden emin olun.
