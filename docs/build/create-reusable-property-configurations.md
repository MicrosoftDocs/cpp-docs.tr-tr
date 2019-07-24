---
title: Visual Studio proje ayarlarını paylaşma veya yeniden kullanma-C++
ms.date: 07/17/2019
helpviewer_keywords:
- project properties [C++], reusable
ms.openlocfilehash: 9a8f6da3dc754aa9d47d46e26207a02bd1685ea8
ms.sourcegitcommit: 610751254a01cba6ad15fb1e1764ecb2e71f66bf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/18/2019
ms.locfileid: "68313188"
---
# <a name="share-or-reuse-visual-studio-project-settings"></a>Visual Studio projelerinin ayarlarını paylaşma veya yeniden kullanma

Birden çok projede başkalarıyla paylaşabileceğiniz veya yeniden kullanabileceğiniz özel bir ayar grubu oluşturmak için Özellik Yöneticisi kullanarak, yeniden kullanmak veya paylaşmak istediğiniz her proje türü için ayarları depolamak üzere bir *özellik sayfası* (. props dosyası) oluşturmak için  kullanın diğer bir deyişle. Özellik sayfalarını kullanmak, "genel" ayarları oluşturmanın diğer yöntemlerinden çok daha az hataya açıktır. 

> [!IMPORTANT]
> **. Kullanıcı dosyaları ve neden sorunlu olma**
>
> Visual Studio 'nun eski sürümleri, \<. User dosya adı uzantısına sahip olan ve USERPROFILE > \AppData\Local\Microsoft\MSBuild\v4.0\ klasöründe yer alan genel özellik sayfaları kullanıyordu. Bu dosyalar, proje yapılandırmalarına ilişkin özellikleri kullanıcı başına ve bilgisayar başına temelinde ayarladığından artık bu dosyaları önermiyoruz. Bu tür "genel" ayarlar, özellikle de yapı bilgisayarınızda birden fazla platformu hedef aldığınızda yapıları engelleyebilir. Örneğin, hem MFC projeniz hem de Windows Phone projeniz varsa, .user özellikleri bunlardan biri için geçersiz olur. Yeniden kullanılabilir özellik sayfaları daha esnek ve daha güçlüdür.
>
> .user dosyaları halen Visual Studio tarafından yüklenmesine ve özellik devralımında rol oynamasına karşın, bu dosyalar varsayılan olarak boştur. En iyi **Özellik Yöneticisi** Yöntem, projelerinizin Kullanıcı başına, bilgisayar başına ayarlarından bağımsız olarak çalıştığından emin olmak için, bir SCC (kaynak kodu denetimi) ortamında doğru davranışı sağlamak açısından önemlidir.

**Özellik Yöneticisi**görüntülemek için, menü çubuğunda**Özellik Yöneticisi** **görüntüle** > ' yi seçin veya ayarlarınıza bağlı olarak**diğer Windows** > **Özellik Yöneticisi** **görüntüleyin** > .

Birden çok projeye uygulamak istediğiniz ortak, sık kullanılan bir özellik kümesine sahipseniz, bunları kural tarafından bir. props dosya adı uzantısına sahip olan, yeniden kullanılabilir bir *özellik sayfası* dosyasında yakalamak için **Özellik Yöneticisi** kullanabilirsiniz. Özelliklerini sıfırdan ayarlamanıza gerek kalmaması için sayfayı (veya sayfaları) yeni projelere uygulayabilirsiniz.

![Özellik Yöneticisi kısayol menüsü](media/sharingnew.png "Sharingnew")

Her yapılandırma düğümü altında, bu yapılandırma için geçerli olan her bir özellik sayfası için düğümleri görürsünüz. Sistem, projeyi oluştururken uygulama sihirbazında seçtiğiniz seçeneklere göre değerleri ayarlamak için özellik sayfaları ekler. Herhangi bir düğüme sağ tıklayıp Özellikler ' i seçerek bu düğüm için uygulanan özellikleri görüntüleyin. Tüm özellik sayfaları, projenin "ana" özellik sayfasına (MS. cpp. props) otomatik olarak içeri aktarılır ve Özellik Yöneticisi göründükleri sırada değerlendirilir. Değerlendirme sırasını değiştirmek için bunları taşıyabilirsiniz. Daha sonra değerlendirilen Özellik sayfaları, önceden değerlendirilen sayfalardaki değerleri geçersiz kılar. . Vcxproj dosyası,. props ve. targets dosyaları, ortam değişkenleri ve komut satırı içindeki değerlendirmenin sırası hakkında daha fazla bilgi için bkz. [Proje özelliği devralma](project-property-inheritance.md) .

**Yeni proje özellik sayfası ekle** ' yi ve ardından, örneğin, MyProps. props Özellik sayfası ' nı seçerseniz, bir özellik sayfası iletişim kutusu görüntülenir. Bunun MyProps özellik sayfası için geçerli olduğuna dikkat edin; yaptığınız herhangi bir değişiklik proje dosyasına (.vcxproj) değil de sayfaya yazılır.

Aynı özellik doğrudan .vcxproj dosyasında ayarlanmışsa, özellik sayfasındaki özellikler geçersiz kılınır.

Bir özellik sayfasını gerektiği sıklıkta içeri aktarabilirsiniz. Bir çözümdeki birden çok proje, aynı özellik sayfasından ayarları devralabilir ve bir projenin birden fazla sayfası olabilir. Özellik sayfasının kendisi, başka bir özellik sayfasından ayarları devralabilir.

Birden çok yapılandırma için tek bir özellik sayfası da oluşturabilirsiniz. Bunu yapmak için, her yapılandırma için bir özellik sayfası oluşturun, bunlardan biri için kısayol menüsünü açın, **varolan özellik sayfası ekle**' yi seçin ve ardından diğer sayfaları ekleyin. Ancak, tek bir ortak özellik sayfası kullanırsanız, ayarladığınız bir özelliğin sayfanın geçerli olduğu tüm yapılandırmalar için ayarlandığını ve IDE'nin, belirli bir özellik sayfasından hangi projelerin veya diğer özellik sayfalarının devraldığını göstermediğini unutmayın.

Birçok projesi olacak büyük çözümlerde, çözüm düzeyinde bir özellik sayfası oluşturulması yararlı olabilir. Çözüme bir proje eklediğinizde, bu özellik sayfasını projeye eklemek için **Özellik Yöneticisi** kullanın. Proje düzeyinde gerek duyulursa, projeye özgü değerleri ayarlamak için yeni bir özellik sayfası ekleyebilirsiniz.

> [!IMPORTANT]
> .props dosyası bir proje öğesi olarak oluşturulmadığından, varsayılan olarak kaynak denetiminde yer almaz. Dosyayı kaynak denetimine dahil etmek istiyorsanız bir çözüm öğesi olarak el ile ekleyebilirsiniz.

#### <a name="to-create-a-property-sheet"></a>Bir özellik sayfası oluşturmak için

1. Menü çubuğunda**Özellik Yöneticisi** **görüntüle** > ' yi seçin veya**diğer Windows** > **Özellik Yöneticisi** **görüntüleyin** > . **Özellik Yöneticisi** açılır.

2. Özellik sayfasının kapsamını tanımlamak için, geçerli olduğu öğeyi seçin. Bu, belirli bir yapılandırma veya başka bir özellik sayfası olabilir. Bu öğe için kısayol menüsünü açın ve **Yeni proje özellik sayfası ekle**' yi seçin. Bir ad ve konum belirtin.

3. **Özellik Yöneticisi**' de, yeni özellik sayfasını açın ve dahil etmek istediğiniz özellikleri ayarlayın.
