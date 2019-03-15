---
title: Paylaşımı veya resuse Visual Studio Proje ayarları - C++
ms.date: 11/28/2018
helpviewer_keywords:
- project properties [C++], reusable
ms.openlocfilehash: 50e3795a4708a3c15ed25ee7ff6565470ef6989a
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57824126"
---
# <a name="share-or-resuse-visual-studio-project-settings"></a>Paylaşımı veya resuse Visual Studio Proje ayarları

Birden çok proje başkalarıyla paylaşmak ya da yeniden ayarlarının özel bir grup oluşturmak için kullanın **özellik Yöneticisi** oluşturmak için bir *özellik sayfası* (tür her ayarlarını depolamak için .props dosyası) yeniden kullanabilmek veya diğer kişilerle paylaşmak mümkün olmasını istediğiniz proje. Özelliğini kullanarak sayfa çok daha az hata yapmaya açık "Genel" ayarlar oluşturmanın diğer yolu. 

> [!IMPORTANT]
> **.user dosyaları ve sorunlu olmalarının**
>
> Visual Studio'nun önceki sürümlerinde, .kullanıcı dosya adı uzantısı ve bulunan genel özellik sayfalarını kullanılan \<kullanıcı profili > \AppData\Local\Microsoft\MSBuild\v4.0\ klasör. Bu dosyalar, proje yapılandırmalarına ilişkin özellikleri kullanıcı başına ve bilgisayar başına temelinde ayarladığından artık bu dosyaları önermiyoruz. Bu tür "genel" ayarlar, özellikle de yapı bilgisayarınızda birden fazla platformu hedef aldığınızda yapıları engelleyebilir. Örneğin, hem MFC projeniz hem de Windows Phone projeniz varsa, .user özellikleri bunlardan biri için geçersiz olur. Yeniden kullanılabilir özellik sayfaları daha esnek ve daha güçlüdür.
>
> .user dosyaları halen Visual Studio tarafından yüklenmesine ve özellik devralımında rol oynamasına karşın, bu dosyalar varsayılan olarak boştur. En iyi nde bunların başvurusunu silmektir **özellik Yöneticisi** projelerinizin kullanıcıya bağımsız olarak çalıştığından emin olmak için bilgisayar başına ayarları bu bir SCC (kaynak kodu, doğru davranışı sağlamak açısından önemlidir Ortam Denetimi).

Görüntülenecek **özellik Yöneticisi**, menü çubuğunda, **görünümü**, **diğer Windows**, **özellik Yöneticisi**.

Birden çok projeye uygulamak istediğiniz özellikleri ortak ve sık kullanılan bir dizi varsa, kullanabileceğiniz **özellik Yöneticisi** yeniden kullanılabilir Yakalanacak *özellik sayfası* olan kural olarak, dosya bir .props dosya adı uzantısı. Özelliklerini sıfırdan ayarlamanıza gerek kalmaması için sayfayı (veya sayfaları) yeni projelere uygulayabilirsiniz. Erişim için **özellik Yöneticisi**, menü çubuğunda, **görünümü**, **özellik Yöneticisi**.

![Özellik Yöneticisi kısayol menüsünü](media/sharingnew.png "SharingNew")

Her yapılandırma düğümü altında bu yapılandırma için uygulanan her bir özellik sayfası için düğümleri görürsünüz. Sistem projesi oluşturduğunuzda, Uygulama Sihirbazı'nda belirlediğiniz seçeneklere dayanan bir değerler kümesi özellik sayfaları ekler. Herhangi bir düğüme sağ tıklayın ve bu düğüme uygulanan özellikleri görmek için Özellikler'i seçin. Tüm özellik sayfalarının projenin "ana" özellik sayfası (ms.cpp.props) otomatik olarak içeri aktarılır ve özellik Yöneticisi'nde göründükleri sırayla değerlendirilir. Değerlendirme sırasını değiştirmek için bunları taşıyabilirsiniz. Daha sonra hesaplanan özellik sayfalarını sayfalarda daha önce hesaplanan değerler geçersiz kılınır. Bkz: [proje özellik devralma](project-property-inheritance.md) .vcxproj dosyasını, .props ve .targets dosyaları, ortam değişkenleri ve komut satırı değerlendirme sırası hakkında daha fazla bilgi.

Seçerseniz **yeni proje özelliği Sayfası Ekle** ve seçin, örneğin, MyProps.props özellik sayfasını, bir özellik sayfası iletişim kutusu görünür. Bunun MyProps özellik sayfası için geçerli olduğuna dikkat edin; yaptığınız herhangi bir değişiklik proje dosyasına (.vcxproj) değil de sayfaya yazılır.

Aynı özellik doğrudan .vcxproj dosyasında ayarlanmışsa, özellik sayfasındaki özellikler geçersiz kılınır.

Bir özellik sayfasını gerektiği sıklıkta içeri aktarabilirsiniz. Bir çözümdeki birden çok proje, aynı özellik sayfasından ayarları devralabilir ve bir projenin birden fazla sayfası olabilir. Özellik sayfasının kendisi, başka bir özellik sayfasından ayarları devralabilir.

Birden çok yapılandırma için tek bir özellik sayfası da oluşturabilirsiniz. Bunu yapmak için her bir yapılandırma için bir özellik sayfası oluşturun, bunlardan biri için kısayol menüsünü açın, seçin **varolan özellik sayfası Ekle**ve ardından diğer sayfaları ekleyin. Ancak, tek bir ortak özellik sayfası kullanırsanız, ayarladığınız bir özelliğin sayfanın geçerli olduğu tüm yapılandırmalar için ayarlandığını ve IDE'nin, belirli bir özellik sayfasından hangi projelerin veya diğer özellik sayfalarının devraldığını göstermediğini unutmayın.

Birçok projesi olacak büyük çözümlerde, çözüm düzeyinde bir özellik sayfası oluşturulması yararlı olabilir. Çözüme bir proje eklediğinizde, kullanın **özellik Yöneticisi** o özellik sayfasını projeye eklemek için. Proje düzeyinde gerek duyulursa, projeye özgü değerleri ayarlamak için yeni bir özellik sayfası ekleyebilirsiniz.

> [!IMPORTANT]
> .props dosyası bir proje öğesi olarak oluşturulmadığından, varsayılan olarak kaynak denetiminde yer almaz. Dosyayı kaynak denetimine dahil etmek istiyorsanız bir çözüm öğesi olarak el ile ekleyebilirsiniz.

#### <a name="to-create-a-property-sheet"></a>Bir özellik sayfası oluşturmak için

1. Menü çubuğunda, **görünümü**, **özellik Yöneticisi**. **Özellik Yöneticisi** açılır.

2. Özellik sayfasının kapsamını tanımlamak için, geçerli olduğu öğeyi seçin. Bu, belirli bir yapılandırma veya başka bir özellik sayfası olabilir. Bu öğe için kısayol menüsünü açın ve ardından **yeni proje özelliği Sayfası Ekle**. Bir ad ve konum belirtin.

3. İçinde **özellik Yöneticisi**, yeni özellik sayfasını açın ve sonra eklemek istediğiniz özellikleri ayarlayın.
