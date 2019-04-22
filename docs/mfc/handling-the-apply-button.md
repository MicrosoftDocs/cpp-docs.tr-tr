---
title: Uygula Düğmesini İşleme
ms.date: 11/04/2016
helpviewer_keywords:
- Apply button in property sheet
- property sheets, Apply button
ms.assetid: 7e977015-59b8-406f-b545-aad0bfd8d55b
ms.openlocfilehash: 30ee549a334a684deeb4a845f2fc49ee8bbe11db
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58770843"
---
# <a name="handling-the-apply-button"></a>Uygula Düğmesini İşleme

Özellik sayfaları, standart iletişim kutuları bulunmayan bir özellik vardır: Özellik sayfasını kapatmadan önce yaptığınız değişiklikleri uygulamak kullanıcı sağlarlar. Bu yapılır Uygula düğmesini kullanarak. Bu makalede, bu özelliği düzgün şekilde uygulamak için kullanabileceğiniz yöntemler açıklanır.

Kullanıcı iletişim kutusunu kapatmak için Tamam'ı tıkladığında kalıcı iletişim kutuları ayarları genellikle dış bir nesneye uygulayın. Aynı bir özellik sayfası için geçerlidir: Kullanıcı Tamam tıkladığında, yeni özellik sayfası ayarları geçerli olur.

Ancak, kullanıcının özellik sayfası iletişim kutusu kapatmaya gerek kalmadan ayarları kaydetmesine olanak tanıyan isteyebilirsiniz. Uygula düğmesini işlev budur. Uygula düğmesini yalnızca şu anda etkin sayfa geçerli ayarlarını uygulamak yerine dış nesne tüm özellik sayfalarının geçerli ayarlarını uygular.

Varsayılan olarak, Uygula düğmesine her zaman devre dışıdır. Uygun zamanlarda Uygula düğmesini etkinleştirmek için kod yazmanız gerekir ve aşağıda açıklandığı gibi Uygula etkisini uygulamak için kod yazmanız gerekir.

Kullanıcıya Uygula işlevselliği sunmak istemiyorsanız Uygula düğmesini kaldırmak gerekli değildir. Standart özellik sayfası destek gelecekteki Windows sürümlerinde kullanan uygulamalar arasında yaygın olarak, devre dışı bırakılabilir.

Rapor olarak değiştirilen bir sayfası ve Uygula düğmesini etkinleştirmek için çağrı `CPropertyPage::SetModified( TRUE )`. Varsa değiştirilen sayfaların rapor Uygula düğmesini, olup şu anda etkin sayfa değiştirilmiş bağımsız olarak, etkin kalmaya devam eder.

Çağırmalısınız [CPropertyPage::SetModified](../mfc/reference/cpropertypage-class.md#setmodified) her kullanıcı sayfasında herhangi bir ayarı değiştirir. Bir kullanıcı bir ayar sayfasında değiştiğini Algıla yollarından biri açıklanmıştır değişiklik bildirimi işleyicileri her özellik sayfası denetimleri gibi uygulamak için **EN_CHANGE** veya **BN_CLICKED**.

Uygula düğmesini etkisini uygulamak için özellik sayfası sahibi veya başka bir dış nesne özellik sayfalarındaki geçerli ayarları uygulamak için bu uygulamada söylemeniz gerekir. Aynı zamanda, özellik sayfasında Uygula düğmesini çağırarak devre dışı bırakmanız gerekir `CPropertyPage::SetModified( FALSE )` kendi değişikliklerini dış nesne için uygulanan tüm sayfalar için.

Bu işlemin bir örneği için bkz: MFC genel örnek [PROPDLG](../overview/visual-cpp-samples.md).

## <a name="see-also"></a>Ayrıca bkz.

[Özellik sayfaları](../mfc/property-sheets-mfc.md)
