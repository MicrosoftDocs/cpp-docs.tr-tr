---
title: Uygula düğmesini işleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Apply button in property sheet
- property sheets, Apply button
ms.assetid: 7e977015-59b8-406f-b545-aad0bfd8d55b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8286bc15d3bbc3716263bf76b0eea953366b0947
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46405924"
---
# <a name="handling-the-apply-button"></a>Uygula Düğmesini İşleme

Özellik sayfaları, standart iletişim kutuları bulunmayan bir özellik vardır: yapmış özellik sayfasını kapatmadan önce değişiklikleri uygulamak kullanıcı sağlarlar. Bu yapılır Uygula düğmesini kullanarak. Bu makalede, bu özelliği düzgün şekilde uygulamak için kullanabileceğiniz yöntemler açıklanır.

Kullanıcı iletişim kutusunu kapatmak için Tamam'ı tıkladığında kalıcı iletişim kutuları ayarları genellikle dış bir nesneye uygulayın. Aynı bir özellik sayfası için geçerlidir: kullanıcı Tamam tıkladığında, özellik sayfasında yeni ayarları etkili.

Ancak, kullanıcının özellik sayfası iletişim kutusu kapatmaya gerek kalmadan ayarları kaydetmesine olanak tanıyan isteyebilirsiniz. Uygula düğmesini işlev budur. Uygula düğmesini yalnızca şu anda etkin sayfa geçerli ayarlarını uygulamak yerine dış nesne tüm özellik sayfalarının geçerli ayarlarını uygular.

Varsayılan olarak, Uygula düğmesine her zaman devre dışıdır. Uygun zamanlarda Uygula düğmesini etkinleştirmek için kod yazmanız gerekir ve aşağıda açıklandığı gibi Uygula etkisini uygulamak için kod yazmanız gerekir.

Kullanıcıya Uygula işlevselliği sunmak istemiyorsanız Uygula düğmesini kaldırmak gerekli değildir. Standart özellik sayfası destek gelecekteki Windows sürümlerinde kullanan uygulamalar arasında yaygın olarak, devre dışı bırakılabilir.

Rapor olarak değiştirilen bir sayfası ve Uygula düğmesini etkinleştirmek için çağrı `CPropertyPage::SetModified( TRUE )`. Varsa değiştirilen sayfaların rapor Uygula düğmesini, olup şu anda etkin sayfa değiştirilmiş bağımsız olarak, etkin kalmaya devam eder.

Çağırmalısınız [CPropertyPage::SetModified](../mfc/reference/cpropertypage-class.md#setmodified) her kullanıcı sayfasında herhangi bir ayarı değiştirir. Bir kullanıcı bir ayar sayfasında değiştiğini Algıla yollarından biri açıklanmıştır değişiklik bildirimi işleyicileri her özellik sayfası denetimleri gibi uygulamak için **EN_CHANGE** veya **BN_CLICKED**.

Uygula düğmesini etkisini uygulamak için özellik sayfası sahibi veya başka bir dış nesne özellik sayfalarındaki geçerli ayarları uygulamak için bu uygulamada söylemeniz gerekir. Aynı zamanda, özellik sayfasında Uygula düğmesini çağırarak devre dışı bırakmanız gerekir `CPropertyPage::SetModified( FALSE )` kendi değişikliklerini dış nesne için uygulanan tüm sayfalar için.

Bu işlemin bir örneği için bkz: MFC genel örnek [PROPDLG](../visual-cpp-samples.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Özellik sayfaları](../mfc/property-sheets-mfc.md)

