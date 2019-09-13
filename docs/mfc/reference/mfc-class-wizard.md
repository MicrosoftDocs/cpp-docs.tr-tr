---
title: MFC Sınıf Sihirbazı
ms.date: 09/06/2019
f1_keywords:
- vc.wizards.classwizard
helpviewer_keywords:
- MFC Class Wizard
ms.assetid: 8b0dd867-5d07-4214-99be-2a1c1995e6d9
ms.openlocfilehash: be829156d8fea8188a217b2c0a189ac5d6057a7e
ms.sourcegitcommit: 3caf5261b3ea80d9cf14038c116ba981d655cd13
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/11/2019
ms.locfileid: "70907994"
---
# <a name="mfc-class-wizard"></a>MFC Sınıf Sihirbazı

Yeni MFC sınıfları oluşturmak veya projenizdeki mevcut sınıflara ileti ve ileti işleyicileri eklemek için **sınıf Sihirbazı** 'nı kullanın.

**Sınıf Sihirbazı**'nı açmak için üç yol vardır:

- **Proje** menüsünde **sınıf Sihirbazı**' nı seçin.
- **CTRL** > SHIFTX > yazın.
- **Sınıf görünümü**' de, bir sınıfa veya proje düğümüne sağ tıklayın ve **sınıf Sihirbazı**' nı seçin.

![Sınıf Sihirbazı](media/class-wizard.png "MFC sınıf Sihirbazı")

## <a name="uielement-list"></a>UIElement Listesi

- **Project**

   Çözümünüzdeki projenin adı.

   Çözümünüzde açılan liste kutusundan diğer projeleri seçebilirsiniz.

- **Sınıf adı**

   Projenizdeki bir sınıfın adı.

   **Sınıf adı** listesinde bir sınıf seçtiğinizde, sınıftaki veriler, **MFC sınıf Sihirbazı**'ndaki denetimleri doldurur. Bir denetimin değerini değiştirdiğinizde, seçili sınıftaki veriler etkilenir.

- **Sınıf Ekle**

   MFC projenize yeni bir sınıf eklemenizi sağlar.

- **Temel sınıf**

   **Sınıf adında**görüntülenen sınıfın temel sınıfı.

- **Sınıf bildirimi**

   **Sınıf adı** sınıfının bildirildiği sınıf.

   **Sınıf bildirim** kutusu yalnızca içindeki ad, **sınıf uygulamasındaki**addan farklıysa görüntülenir.

- **Kaynak**

   Varsa, **sınıf adındaki**kaynağın kimliği. Aksi takdirde, **kaynak** kutusu boştur.

- **Sınıf uygulama**

   Sınıf **adındaki**sınıfın uygulamasını içeren dosyanın adı.

   Oka tıklayarak farklı bir uygulama dosyası seçebilirsiniz. Aşağıdaki tabloda kullanılabilir seçenekler listelenmektedir.

   |Seçenek|Açıklama|
   |------------|-----------------|
   |**Dosya Aç**|Sınıf sihirbazından çıkar ve geçerli sınıf uygulama dosyasını açar.|
   |**Içeren klasörü aç**|Geçerli sınıf uygulama dosyasını içeren klasörü açar.|
   |**Tam yolu panoya kopyala**|Geçerli uygulama dosyasının yolunu panoya kopyalar.|

- **Komut**

   Bir komutu ve ileti işleyicisini eklemenizi, silmenizi, düzenlemenizi veya aramanızı sağlar.

   Bir işleyici eklemek için **Işleyici Ekle**' ye tıklayın veya **nesne kimlikleri** listesi veya **iletiler** listesindeki bir öğeye çift tıklayın. Sonuç işlevi adı, KIMLIĞI ve iletisi, **üye işlevleri** listesinde görüntülenir.

   Bir işleyiciyi silmek için **üye işlevleri** listesinden bir öğe seçin ve ardından **işleyiciyi Sil**' e tıklayın.

   Bir işleyiciyi değiştirmek için **üye işlevleri** listesinde karşılık gelen öğeye çift tıklayın. Veya liste kutusunda bir öğe seçin ve ardından **kodu Düzenle**' ye tıklayın.

- **İletiler**

   İleti ve ileti işleyicisini eklemenizi, silmenizi, düzenlemenizi veya aramanızı sağlar.

   Bir işleyici eklemek için **Işleyici Ekle**' ye tıklayın veya **iletiler** listesindeki bir öğeye çift tıklayın.

   Özel bir ileti eklemek için **özel Ileti Ekle** ' ye tıklayın veya ENTER tuşuna basın ve ardından **özel ileti Ekle** iletişim kutusunda değerleri belirtin. Bu iletişim kutusunda, işletim sistemi genelinde benzersiz olması garanti edilen bir pencere iletisini işlemek için **kayıtlı ileti** ' i de seçebilirsiniz.

- **Sanal İşlevler**

   Sanal bir işlev veya geçersiz kılınan bir sanal işlev eklemenize, silmenize, düzenlemenize veya aramanıza olanak tanır.

- **Üye değişkenleri**

   Bir üye değişkeni eklemenizi, silmenizi, düzenlemenizi veya aramanızı sağlar.

- **Yöntemler**

   Bir Yöntemi eklemenize, silmenize veya aramanıza izin verir ve ayrıca bir metodun tanımına veya bildirimine gidebilirsiniz.

   Bir yöntem eklemek **için yöntem Ekle ' ye tıklayın ve**ardından **Yöntem Ekle** iletişim kutusunda değerleri belirtin.

   Bir yöntemi silmek için, **Yöntemler** listesinden bir öğe seçin ve ardından **yöntemi Sil**' e tıklayın.

   Bir bildirimi göstermek için, **Yöntemler** listesinden bir öğe seçin ve ardından **bildirime git ' e tıklayın.**

   Bir tanımı göstermek için, **Yöntemler** listesindeki bir öğeye çift tıklayın. İsterseniz, **Yöntemler** listesinden bir öğe seçin ve ardından **Tanıma Git** düğmesine tıklayın.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıf ekleme](../../ide/adding-a-class-visual-cpp.md)
