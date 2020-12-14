---
description: 'Hakkında daha fazla bilgi edinin: Uygula düğmesini Işleme'
title: Uygula Düğmesini İşleme
ms.date: 11/04/2016
helpviewer_keywords:
- Apply button in property sheet
- property sheets, Apply button
ms.assetid: 7e977015-59b8-406f-b545-aad0bfd8d55b
ms.openlocfilehash: a626dcab04d68d19efba79465bfca46545ff6670
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97254943"
---
# <a name="handling-the-apply-button"></a>Uygula Düğmesini İşleme

Özellik sayfaları standart iletişim kutularının olmadığı bir özelliğe sahiptir: kullanıcıların, özellik sayfasını kapatmadan önce yaptıkları değişiklikleri uygulamasına izin verir. Bu, Uygula düğmesi kullanılarak yapılır. Bu makalede, bu özelliği düzgün şekilde uygulamak için kullanabileceğiniz yöntemler ele alınmaktadır.

Kalıcı iletişim kutuları genellikle Kullanıcı iletişim kutusunu kapatmak için Tamam ' a tıkladığında ayarları bir dış nesneye uygular. Özellik sayfası için de aynı değer geçerlidir: Kullanıcı Tamam ' ı tıklattığında, özellik sayfasındaki yeni ayarlar geçerli olur.

Ancak, kullanıcının özellik sayfası iletişim kutusunu kapatmak zorunda kalmadan ayarları kaydetmesine izin vermek isteyebilirsiniz. Bu, Uygula düğmesinin işlevidir. Uygula düğmesi, şu anda etkin olan sayfanın yalnızca geçerli ayarlarını uygulamanın aksine, tüm özellik sayfalarındaki geçerli ayarları dış nesneye uygular.

Varsayılan olarak, Uygula düğmesi her zaman devre dışıdır. Uygula düğmesini uygun zamanlarda etkinleştirmek için kod yazmanız gerekir ve aşağıda açıklandığı gibi, Uygula efektini uygulamak için kod yazmanız gerekir.

Kullanıcıya uygulama işlevselliği sunmak istemiyorsanız, Uygula düğmesinin kaldırılması gerekli değildir. Windows 'un gelecek sürümlerinde kullanılabilen standart özellik sayfası desteğini kullanan uygulamalar arasında ortak olacak şekilde devre dışı bırakabilirsiniz.

Bir sayfayı değiştirilme olarak bildirmek ve Uygula düğmesini etkinleştirmek için çağırın `CPropertyPage::SetModified( TRUE )` . Sayfaların herhangi biri değiştiriliyorsa, geçerli etkin sayfanın değiştirilip değiştirilmediğini bakılmaksızın Uygula düğmesi etkin kalır.

Kullanıcı sayfadaki herhangi bir ayarı değiştirdiğinde [CPropertyPage:: SetModified](reference/cpropertypage-class.md#setmodified) öğesini çağırmanız gerekir. Bir kullanıcının sayfadaki bir ayarı değiştirdiğini algılamaya yönelik bir yol, özellik sayfasındaki **EN_CHANGE** veya **BN_CLICKED** gibi her bir denetim için değişiklik bildirimi işleyicilerini uygulamadır.

Uygula düğmesinin etkisini uygulamak için özellik sayfası, geçerli ayarları özellik sayfalarında uygulamak üzere, sahibine veya uygulamadaki başka bir dış nesneye sahip olmalıdır. Aynı zamanda, özellik sayfası `CPropertyPage::SetModified( FALSE )` değişikliklerini dış nesneye uygulayan tüm sayfaları çağırarak Uygula düğmesini devre dışı bırakmalıdır.

Bu işleme bir örnek için bkz. MFC genel örnek [propdlg](../overview/visual-cpp-samples.md).

## <a name="see-also"></a>Ayrıca bkz.

[Özellik sayfaları](property-sheets-mfc.md)
