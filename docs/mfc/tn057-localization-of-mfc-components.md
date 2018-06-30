---
title: 'TN057: MFC bileşenlerini yerelleştirme | Microsoft Docs'
ms.custom: ''
ms.date: 06/28/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.mfc.components
dev_langs:
- C++
helpviewer_keywords:
- components [MFC], localizing
- TN057
- resources [MFC], localization
- localization [MFC], MFC resources
- localization [MFC], MFC components
- MFC DLLs [MFC], localizing
- DLLs [MFC], localizing MFC
- localization [MFC], resources
ms.assetid: 5376d329-bd45-41bd-97f5-3d895a9a0af5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ec786277432ab1ce47614c3afac627733edc4985
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37121163"
---
# <a name="tn057-localization-of-mfc-components"></a>TN057: MFC Bileşenlerini Yerelleştirme

> [!NOTE]
> İlk çevrimiçi belgelerinde eklenmiştir beri aşağıdaki Teknik Not güncelleştirilmemiş. Sonuç olarak, bazı yordamlar ve konuları güncel veya yanlış olması olabilir. En son bilgiler için çevrimiçi belgeleri dizindeki ilgi konuyu aramak önerilir.

Bu Not tasarımları ve bir uygulama veya bir OLE denetlerseniz, bileşen yerelleştirme için kullanabileceğiniz yordamları veya MFC kullanan bir DLL bazıları açıklanmaktadır.

## <a name="overview"></a>Genel Bakış

Gerçekten ne zaman çözümlemek için iki sorunları vardır, MFC kullanan bir bileşeni yerelleştirme. İlk olarak, kendi kaynakları yerelleştirme — dizeler, iletişim kutuları ve bileşeniniz için özel kaynaklar. MFC ayrıca kullanılarak oluşturulan çoğu bileşenleri içerir ve MFC tarafından tanımlanan kaynak sayısı kullanın. Yerelleştirilmiş MFC kaynakları de sağlamanız gerekir. Neyse ki, çeşitli diller MFC tarafından zaten sağlanır.

Ayrıca, bileşeniniz, hedef ortamda (Avrupa veya DBCS etkin ortamı) çalıştırmak için hazırlıklı olmalıdır. Çoğunlukla, bu uygulamanızın yüksek bit kümesiyle karakterleri doğru şekilde davranma ve çift baytlı karakter dizeleri işleme bağlıdır. Kurulum sırasında prize takılı yalnızca farklı kaynaklar tüm platformlarda kullanılan tek bir dünya çapında ikili olması mümkündür gibi MFC, varsayılan olarak, her ikisi de bu ortamlar için etkinleştirilir.

## <a name="localizing-your-components-resources"></a>Bileşenin kaynakları yerelleştirme

Uygulama veya DLL yerelleştirme yalnızca kaynakları hedef dil karşılayan kaynakları ile değiştirerek içermelidir. Kendi kaynaklar için bu oldukça basittir: kaynakları kaynak düzenleyicisinde düzenleyin ve uygulamanızı oluşturun. Kodunuzun doğru hiçbir dizeleri veya yerelleştirme sabit kodlanmış C++ kaynak kodu içine - istediğiniz metin olacaktır yazılmışsa tüm yerelleştirme kaynaklarını değiştirerek yapılabilir. Aslında, tüm sağlama yerelleştirilmiş bir sürümün bile özgün kod derleme içermeyen şekilde bileşeniniz uygulayabilirsiniz. Bu daha karmaşıktır, ancak iyi, ve MFC için seçilen mekanizmadır. Bir uygulamanın kaynak düzenleyicisine EXE veya DLL dosyasını yüklerken ve kaynakları doğrudan düzenleme yerelleştirme mümkündür. Olası sırasında uygulama yapılamıyorsa, uygulamanızın yeni bir sürümünü oluşturmak her zaman bu değişikliklerin gerektirir.

Bunu önlemek için bir uydu DLL olarak da adlandırılan ayrı bir DLL içinde tüm kaynakları bulmak için yoludur. Bu DLL ardından dinamik olarak çalışma zamanında yüklenir ve kaynakları yerine bu DLL'in tüm kodunuz ile ana modülden yüklenir. MFC doğrudan bu yaklaşım destekler. UYGULAMAM adlı bir uygulamayı göz önünde bulundurun. EXE; MYRES adlı DLL'de bulunan kaynaklarının tümü olabilir. DLL. Uygulamanın içinde `InitInstance` bu DLL yüklenemedi ve MFC kaynakları o konumdan yüklemek neden aşağıdaki gerçekleştirmelisiniz:

```cpp
CMyApp::InitInstance()
{
    // one of the first things in the init code
    HINSTANCE hInst = LoadLibrary("myres.dll");

    if (hInst != NULL)
        AfxSetResourceHandle(hInst);

    // other initialization code would follow
    // ...
}
```

Daha sonra MFC kaynakları yerine bu DLL myapp.exe dosyasından yüklemek. Tüm kaynaklar, ancak bu DLL'deki mevcut olması gerekir; MFC Uygulama örneği belirli bir kaynak aramak üzere aranamaz. Bu teknik OLE denetimleri yanı sıra eşit için iyi Normal MFC DLL'leri geçerlidir. Kurulum programı MYRES'ün uygun sürümüne kopyalamak. DLL hangi kaynak yerel ayara bağlı olarak, kullanıcı ister.

Bir kaynak oluşturmak oldukça kolaydır yalnızca DLL. DLL projesi oluşturma, ekleme. RC için dosya ve gerekli kaynakları ekleyin. Bu teknik kullanmayan varolan projesini varsa, bu projeden kaynakları kopyalayabilirsiniz. Kaynak dosyası projeye eklendikten sonra projeyi derlemek neredeyse hazırsınız demektir. Bağlayıcı dahil etmek için seçenekleri ayarlayın tek şey yapmanız gerekir **/NOENTRY**. Bu bağlayıcı DLL hiçbir giriş noktası - olduğunu söyler kod olduğundan, hiçbir giriş noktası yok.

> [!NOTE]
> Visual C++ 4.0 ve üzeri Kaynak Düzenleyici başına birden çok dili destekler. RC dosyası. Bu tek bir projede yerelleştirme yönetmek çok kolay hale. Her dil için kaynakları kaynak Düzenleyicisi tarafından oluşturulan önişlemci yönergeleri tarafından denetlenir.

## <a name="using-the-provided-mfc-localized-resources"></a>Yerelleştirilmiş kaynakları sağlanan MFC kullanma

MFC gelen iki şey, oluşturduğunuz herhangi bir MFC Uygulama kullanır: kod ve kaynakları. Diğer bir deyişle, MFC çeşitli hata iletileri, yerleşik iletişim kutuları ve MFC sınıfları tarafından kullanılan kaynaklar vardır. Tamamen uygulamanızı yerelleştirme için yalnızca değil, uygulamanızın kaynakları, aynı zamanda doğrudan MFC'den gelen kaynakları yerelleştirme gerekir. MFC birkaç farklı dildeki kaynak dosyaları, hedeflediğiniz dil MFC zaten desteklediği dillerden biriyle ise, bu yerelleştirilmiş kaynakları kullanmasını sağlamak yeterlidir böylece otomatik olarak sağlar.

Bu makalenin yazıldığı sırada MFC Çince, Almanca, İspanyolca, Fransızca, İtalyanca, Japonca ve Kore dili destekler. Bu yerelleştirilmiş sürümleri içeren MFC\INCLUDE\L.* dosyalardır ('L' anlamına gelir yerelleştirilmiş) dizinler. Almanca MFC\INCLUDE\L.DEU örneğin dosyalardır. MFC\INCLUDE içinde bulunan dosyalar yerine RC bu dosyaları kullanmak uygulamanızı neden ekleyin bir `/IC:\PROGRAM FILES\MICROSOFT VISUAL STUDIO .NET 2003\VC7\MFC\INCLUDE\L.DEU` RC komut satırı için (yalnızca bir örnek; bölgeniz, Visual C yüklediğiniz dizin yanı sıra seçim yerine gerekir ++).

MFC ile uygulamanızı statik olarak bağlanıyorsa yukarıdaki yönergeler çalışır. Dinamik olarak (Bu AppWizard varsayılan olduğundan) uygulamaların çoğu bağlayın. Bu senaryoda, yalnızca dinamik olarak kodudur bağlı - kadar kaynak yok. Sonuç olarak, uygulamanızda kaynaklarınızı yerelleştirebilirsiniz, ancak varsa MFC uygulaması kaynakları hala MFC7x.DLL (veya sonraki bir sürümünü) veya MFC7xLOC.DLL yüklenecek. Bu iki farklı açıları yaklaşımını.

Daha karmaşık yaklaşım sevk yerelleştirilmiş MFC7xLOC.DLLs birini (örneğin, Almanca için MFC7xDEU, İspanyolca, vb. için MFC7xESP.DLL) veya sonraki bir sürümünü ve kullanıcı uygulamanızı yüklendiğinde uygun MFC7xLOC.DLL sistem dizinine yükler. Bu, geliştirici ve son kullanıcı için çok karmaşık olabilir ve bu nedenle önerilmez. Bkz: [Teknik Not 56](../mfc/tn056-installation-of-localized-mfc-components.md) Bu teknik ve onun uyarılar hakkında daha fazla bilgi için.

Kolay ve güvenli bir yaklaşım, uygulama veya DLL kendisini (veya kendi uydu birini kullanıyorsanız, DLL) yerelleştirilmiş MFC kaynakları eklemektir. Bu MFC7xLOC.DLL düzgün yükleme sorunları önler. Aynı yönergeleri (düzgün yerelleştirilmiş kaynaklar işaret edecek şekilde RC komut satırı ayarlama yukarıda) verilen statik çalışması için bunu yapmak için ayrıca kaldırmalısınız dışındaki `/D_AFXDLL` tanımlayan AppWizard tarafından eklendi. Zaman `/D_AFXDLL` olan tanımlı, AFXRES. Gerçekte (bunlar MFC DLL'leri yerine çekebilir çünkü) H (ve diğer MFC RC dosyaları) herhangi bir kaynağa tanımlamayın.

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya Göre Teknik Notlar](../mfc/technical-notes-by-number.md)  
[Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)  
