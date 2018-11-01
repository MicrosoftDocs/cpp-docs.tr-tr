---
title: 'Nasıl yapılır: C++ proje (tek başına) dışındaki kaynak betik dosyasını açın'
ms.date: 11/04/2016
f1_keywords:
- vc.editors.resource
helpviewer_keywords:
- resources [C++], viewing
- rc files [C++], viewing resources
- .rc files [C++], viewing resources
- resource script files [C++], viewing resources
ms.assetid: bc350c60-178d-4c5d-9a7e-6576b0c936e4
ms.openlocfilehash: 43b245c1d19e7468a9433473eb49dc970316eba5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50529083"
---
# <a name="how-to-open-a-resource-script-file-outside-of-a-c-project-standalone"></a>Nasıl yapılır: C++ proje (tek başına) dışındaki kaynak betik dosyasını açın

Bir proje açmak zorunda kalmadan bir .rc dosyasındaki kaynakları görüntüleyebilirsiniz. .Rc dosyasının'te açılmasını aksine bir belge penceresi açılır [kaynak görünümü](../windows/resource-view-window.md) penceresi (dosya içinde bir proje açıkken çalıştığı gibi).

> [!NOTE]
> Bazı komutlar yalnızca dosya açılan tek başına (proje dışında) olduğunda kullanılabilir olmadığından önemli bir fark budur. Dosyanın dışında bir proje açıldığında, örneğin, yalnızca bir dosyayı farklı bir biçimde veya farklı bir dosya adı olarak kaydedebilirsiniz ( **Kaydet** komutu, bir dosya içinde bir proje açıldığında kullanılamaz).

### <a name="to-open-an-rc-file-outside-a-project"></a>Bir proje dışında bir .rc dosyasını açmak için

1. Gelen **dosya** menüsünde seçin **açık**, ardından **dosya**.

2. İçinde **açık dosya** iletişim kutusunda, görüntülemek, dosyayı vurgulayın ve tıklayın istediğiniz kaynak betik dosyasına gidin **açık**.

   > [!NOTE]
   > İlk proje açarsanız (**dosya**, **açın**, **proje**), bazı komutlar için kullanılabilir olmayacak. "Tek başına" dosyasını açıp, proje yüklemeden açmadan anlamına gelir.

Açın ve kaynak dosyasını metin biçiminde görüntülemek için bkz: [kaynak betiği (.rc) dosya düzenleme](../windows/how-to-open-a-resource-script-file-in-text-format.md).

### <a name="to-open-multiple-rc-files-outside-a-project"></a>Birden çok .rc dosyası bir proje dışında açmak için

1. Tek başına hem de kaynak dosyalarını açın. Örneğin, açmak `Source1.rc` ve `Source2.rc`.

   1. Gelen **dosya** menüsünde seçin **açık**, ardından **dosya**.

   2. İçinde **Dosya Aç** iletişim kutusunda, açmak istediğiniz ilk kaynak betik dosyasına gidin (`Source1.rc`), dosyayı vurgulayın ve tıklayın **açın**.

   3. İkinci .rc dosyasını açmak için önceki adımı yineleyin (`Source2.rc`).

       .Rc dosyaları artık ayrı bir belge pencerelerinde açıktır.

2. Her iki .rc dosyası açıkken, aynı anda görebilecek şekilde pencereleri döşe:

   - Gelen **penceresi** menüsünde seçin **yeni yatay sekme grubu** veya **yeni bir dikey sekme grubu**.

       \- veya -

   - .Rc dosyaları birine sağ tıklayın ve seçin **yeni yatay sekme grubu** veya **yeni bir dikey sekme grubu** kısayol menüsünden.

> [!NOTE]
> Projenize bir .rc dosyası yoksa, lütfen bkz [yeni bir kaynak betik dosyası oluşturma](../windows/how-to-create-a-resource-script-file.md).

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[Kaynak dosyaları](../windows/resource-files-visual-studio.md)<br/>
[Kaynak Düzenleyicileri](../windows/resource-editors.md)