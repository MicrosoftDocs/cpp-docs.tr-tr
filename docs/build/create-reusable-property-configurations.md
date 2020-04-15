---
title: Visual Studio proje ayarlarını paylaşın veya yeniden kullanın - C++
ms.date: 07/17/2019
helpviewer_keywords:
- project properties [C++], reusable
ms.openlocfilehash: bcf54be0531c7150c1506eb6f5dda2b5bc95161f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328699"
---
# <a name="share-or-reuse-visual-studio-project-settings"></a>Visual Studio projelerinin ayarlarını paylaşma veya yeniden kullanma

Başkalarıyla paylaşabileceğiniz veya birden çok projede yeniden kullanabileceğiniz özel bir ayar grubu oluşturmak için, yeniden kullanmak veya başkalarıyla paylaşmak istediğiniz her tür proje için ayarları depolamak için bir *özellik sayfası* (.sahne dosyası) oluşturmak için **Özellik Yöneticisi'ni** kullanın. Özellik sayfaları kullanmak, "genel" ayarlar oluşturmanın diğer yollarından çok daha az hataya eğilimlidir.

> [!IMPORTANT]
> **.user dosyaları ve neden sorunlu oldukları**
>
> Visual Studio'nun önceki sürümlerinde .kullanıcı dosya adı uzantısı olan ve \<kullanıcı profilinde bulunan>\AppData\Local\Microsoft\MSBuild\v4.0\ klasöründe bulunan genel özellik sayfaları kullanılmıştır. Bu dosyalar, proje yapılandırmalarına ilişkin özellikleri kullanıcı başına ve bilgisayar başına temelinde ayarladığından artık bu dosyaları önermiyoruz. Bu tür "genel" ayarlar, özellikle de yapı bilgisayarınızda birden fazla platformu hedef aldığınızda yapıları engelleyebilir. Örneğin, hem MFC projeniz hem de Windows Phone projeniz varsa, .user özellikleri bunlardan biri için geçersiz olur. Yeniden kullanılabilir özellik sayfaları daha esnek ve daha güçlüdür.
>
> .user dosyaları halen Visual Studio tarafından yüklenmesine ve özellik devralımında rol oynamasına karşın, bu dosyalar varsayılan olarak boştur. En iyi yöntem, projelerinizin kullanıcı başına herhangi bir kullanıcı başına, bilgisayar başına ayarlardan bağımsız olarak çalışmasını sağlamak için **Property Manager'da** kendilerine yapılan başvuruyu silmektir Bu, Bir SCC (kaynak kodu denetimi) ortamında doğru davranışı sağlamak için önemlidir.

Özellik **Yöneticisi'ni**menü çubuğunda görüntülemek için, ayarlarınıza bağlı olarak**Özellik Yöneticisi'ni** **görüntüle** > veya**Diğer Windows** > **Özellik Yöneticisi'ni** **Görüntüle'yi** > seçin.

Birden çok projeye uygulamak istediğiniz yaygın ve sık kullanılan bir özellik kümeniz varsa, bunları yeniden kullanılabilir *özellik sayfası* dosyasında yakalamak için **Özellik Yöneticisi'ni** kullanabilirsiniz ve bu özellik kuralına göre bir .props dosya adı uzantısı vardır. Özelliklerini sıfırdan ayarlamanıza gerek kalmaması için sayfayı (veya sayfaları) yeni projelere uygulayabilirsiniz.

![Emlak Yöneticisi kısayol menüsü](media/sharingnew.png "PaylaşımYeni")

Her yapılandırma düğümüaltında, bu yapılandırma için geçerli olan her özellik sayfası için düğümler görürsünüz. Sistem, projeyi oluştururken uygulama sihirbazında seçtiğiniz seçeneklere göre değerleri ayarlayan özellik sayfaları ekler. Herhangi bir düğümü sağ tıklatın ve bu düğüm için geçerli özellikleri görmek için Özellikler'i seçin. Tüm özellik sayfaları otomatik olarak projenin "ana" özellik sayfasına (ms.cpp.props) alınır ve Emlak Yöneticisi'nde göründükleri sırada değerlendirilir. Değerlendirme sırasını değiştirmek için taşıyabilirsiniz. Daha sonra değerlendirilen özellik sayfaları, daha önce değerlendirilmiş sayfalardaki değerleri geçersiz kılar. .vcxproj dosyasındaki değerlendirme sırası, .props ve .targets dosyaları, ortam değişkenleri ve komut satırı hakkında daha fazla bilgi için [Project özellik devradına](project-property-inheritance.md) bakın.

**Yeni Proje Özellik Sayfası Ekle'yi** seçin ve ardından örneğin MyProps.props özellik sayfasını seçerseniz, bir özellik sayfası iletişim kutusu görüntülenir. Bunun MyProps özellik sayfası için geçerli olduğuna dikkat edin; yaptığınız herhangi bir değişiklik proje dosyasına (.vcxproj) değil de sayfaya yazılır.

Aynı özellik doğrudan .vcxproj dosyasında ayarlanmışsa, özellik sayfasındaki özellikler geçersiz kılınır.

Bir özellik sayfasını gerektiği sıklıkta içeri aktarabilirsiniz. Bir çözümdeki birden çok proje, aynı özellik sayfasından ayarları devralabilir ve bir projenin birden fazla sayfası olabilir. Özellik sayfasının kendisi, başka bir özellik sayfasından ayarları devralabilir.

Birden çok yapılandırma için tek bir özellik sayfası da oluşturabilirsiniz. Bunu yapmak için, her yapılandırma için bir özellik sayfası oluşturun, bunlardan biri için kısayol menüsünü açın, **Varolan Özellik Sayfası Ekle'yi**seçin ve ardından diğer sayfaları ekleyin. Ancak, bir ortak özellik sayfası kullanıyorsanız, bir özellik ayarladığınızda, sayfanın uygulandığı tüm yapılandırmalar için ayarlandığına ve IDE'nin belirli bir özellik sayfasından hangi projelerin veya diğer özellik sayfalarının devraldığını göstermediğini unutmayın.

Birçok projesi olacak büyük çözümlerde, çözüm düzeyinde bir özellik sayfası oluşturulması yararlı olabilir. Çözüme bir proje eklediğinizde, projeye özellik sayfasını eklemek için **Özellik Yöneticisi'ni** kullanın. Proje düzeyinde gerek duyulursa, projeye özgü değerleri ayarlamak için yeni bir özellik sayfası ekleyebilirsiniz.

> [!IMPORTANT]
> Bir .props dosyası varsayılan olarak kaynak denetimine katılmaz, çünkü proje öğesi olarak oluşturulmaz. Dosyayı kaynak denetimine dahil etmek istiyorsanız bir çözüm öğesi olarak el ile ekleyebilirsiniz.

#### <a name="to-create-a-property-sheet"></a>Bir özellik sayfası oluşturmak için

1. Menü çubuğunda,**Özellik Yöneticisi'ni** **Görüntüle** > veya**Diğer Windows** > **Özellik Yöneticisi'ni** **görüntüle'yi** > seçin. **Emlak Yöneticisi** açılır.

2. Özellik sayfasının kapsamını tanımlamak için, geçerli olduğu öğeyi seçin. Bu, belirli bir yapılandırma veya başka bir özellik sayfası olabilir. Bu öğeiçin kısayol menüsünü açın ve ardından **Yeni Proje Özellik Sayfası Ekle'yi**seçin. Bir ad ve konum belirtin.

3. **Property**Manager'da, yeni özellik sayfasını açın ve eklemek istediğiniz özellikleri ayarlayın.
