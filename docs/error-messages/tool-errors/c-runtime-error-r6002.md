---
title: C Çalışma Zamanı Hatası R6002
ms.date: 11/04/2016
f1_keywords:
- R6002
helpviewer_keywords:
- R6002
ms.assetid: 8fbbe65a-9c43-459e-8342-e1f6d1cef7d0
ms.openlocfilehash: f8b5fe69c9fd688f4d0a181176cda247cde9ac11
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62380545"
---
# <a name="c-runtime-error-r6002"></a>C Çalışma Zamanı Hatası R6002

kayan nokta desteği yüklenmedi

Gerekli kayan nokta kitaplığı bağlı değil.

> [!NOTE]
> Bir uygulama çalıştırırken bu hatayla karşılaşırsanız, dahili bir sorun olduğundan uygulaması kapatıldı. Bu hatanın birkaç olası nedeni vardır, ancak uygulamanın koddaki bir hata veya belirli bir bilgisayar işlemci için oluşturulan bir uygulamayı çalıştırma denemesi genellikle neden olur.
>
> Bu hatayı düzeltmek için aşağıdaki adımları deneyebilirsiniz:
>
> - Kullanım **uygulamalar ve Özellikler** veya **programlar ve Özellikler** sayfasını **Denetim Masası** onarın veya programı yeniden yükleyin.
> - Denetleme **Windows Update** içinde **Denetim Masası** yazılım güncelleştirmeleri için.
> - Uygulamanın güncelleştirilmiş bir sürümünü denetleyin. Sorun devam ederse uygulama satıcısına başvurun.

**Programcıları için bilgi**

Kayan nokta kitaplığı bağlanmadı, uygulamanızda bu hata oluşabilir. Bu nedenlerden biri için denetleyin:

- Bir biçim dizesi için bir `printf_s` veya `scanf_s` işlevi yer alan bir kayan nokta biçim belirtimi ve programın herhangi bir kayan nokta değerleri veya değişkenleri içermiyordu. Bu sorunu gidermek için kayan nokta biçim belirtimi için karşılık gelen bir kayan noktalı bağımsız değişken kullanın veya bir kayan nokta ataması programda başka bir yerde gerçekleştirin. Bu, kayan nokta desteği yüklenmesine neden olur.

- Derleyici, kayan nokta desteği yalnızca gerekli olduğunda yükleyerek bir programın boyutu en aza indirir. Gerekli kayan nokta yordamları yüklemeyecek şekilde biçim dizeleri, derleyicinin kayan nokta işlemleri veya kayan nokta biçim belirtimleri algılayamaz. Bu sorunu gidermek için bir kayan nokta biçim belirtimi kullanın ve bir kayan noktalı bağımsız değişken sağlayın veya bir kayan nokta ataması programda başka bir yerde gerçekleştirin. Bu, kayan nokta desteği yüklenmesine neden olur.

- Programa bağlandığında bir karma dil programda bir C Kitaplığı FORTRAN kitaplığa önce belirtildi. Yeniden bağlayın ve en son C Kitaplığı belirtin.