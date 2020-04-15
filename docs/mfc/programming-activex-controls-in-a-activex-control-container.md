---
title: 'ActiveX Denetim Kapsayıcıları: Bir ActiveX Denetim Kapsayıcısındaki ActiveX Denetimlerini Programlama'
ms.date: 09/12/2018
helpviewer_keywords:
- ActiveX control containers [MFC], accessing ActiveX controls
- Confirm Classes dialog box
- wrapper classes [MFC], ActiveX controls
- ActiveX control containers [MFC], wrapper classes
- ActiveX controls [MFC], accessing
- MFC ActiveX controls [MFC], accessing in containers
- header files [MFC], for ActiveX control wrapper class
- wrapper classes [MFC], using
- ActiveX controls [MFC], wrapper classes
ms.assetid: ef9b2480-92d6-4191-b16e-8055c4fd7b73
ms.openlocfilehash: 9620f4d47197147db4972c9f2024f6018a705902
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371182"
---
# <a name="activex-control-containers-programming-activex-controls-in-an-activex-control-container"></a>ActiveX Denetim Kapsayıcıları: Bir ActiveX Denetim Kapsayıcısındaki ActiveX Denetimlerini Programlama

Bu makalede, katıştırılmış ActiveX denetimlerinin açıkta kalan [yöntemlerine](../mfc/mfc-activex-controls-methods.md) ve [özelliklerine](../mfc/mfc-activex-controls-properties.md) erişme işlemi açıklanmaktadır.

>[!IMPORTANT]
> ActiveX, yeni geliştirme için kullanılmaması gereken eski bir teknolojidir. ActiveX'in yerini alabilecek modern teknolojiler hakkında daha fazla bilgi için [ActiveX Denetimleri'ne](activex-controls.md)bakın.

Temel olarak, aşağıdaki adımları izleyeceksiniz:

1. Galeri'yi kullanarak [ActiveX kapsayıcı projesine activex denetimi ekleyin.](../mfc/inserting-a-control-into-a-control-container-application.md)

1. ActiveX denetim sarıcı sınıfıyla aynı türden [bir üye değişken](../mfc/activex-control-containers-connecting-an-activex-control-to-a-member-variable.md) (veya başka bir erişim biçimi) tanımlayın.

1. [Sarmalayıcı sınıfının](#_core_programming_the_activex_control) önceden tanımlanmış üye işlevlerini kullanarak ActiveX denetimini programla.

Bu tartışma için ActiveX denetim desteğine sahip iletişim tabanlı bir proje (Kapsayıcı adlı) oluşturduğunuzu varsayalım. Circ örnek kontrolü, Circ, ortaya çıkan projeye eklenecektir.

Circ denetimi projeye (adım 1) takıldıktan sonra, uygulamanın ana iletişim kutusuna Circ denetiminin bir örneğini ekleyin.

## <a name="procedures"></a>Yordamlar

#### <a name="to-add-the-circ-control-to-the-dialog-template"></a>İletişim şablonuna Circ denetimini eklemek için

1. ActiveX kontrol konteyneri projesini yükleyin. Bu örnekte, `Container` projeyi kullanın.

1. Kaynak Görünümü sekmesini tıklatın.

1. **İletişim** klasörünü açın.

1. Ana iletişim kutusu şablonuna çift tıklayın. Bu örnekte, **IDD_CONTAINER_DIALOG.**

1. Araç Kutusu'ndaki Circ denetim simgesini tıklatın.

1. Circ denetimini eklemek için iletişim kutusu içindeki bir noktayı tıklatın.

1. **Dosya** menüsünden, iletişim kutusu şablonundaki tüm değişiklikleri kaydetmek için **Tümlerini Kaydet'i** seçin.

## <a name="modifications-to-the-project"></a>Projede Yapılan Değişiklikler

Kapsayıcı uygulamasının Circ denetimine erişmesini sağlamak için Visual C++`CCirc`otomatik olarak sarıcı sınıfı ( ) uygulama dosyasını ekler (. ) CPP) Konteyner projesine ve sarmalayıcı sınıfı üstbilgisine (. H) iletişim kutusu üstbilgi dosyasına dosya:

[!code-cpp[NVC_MFC_AxCont#1](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_1.h)]

## <a name="the-wrapper-class-header-h-file"></a><a name="_core_the_wrapper_class_header_28h29_file"></a>Sarıcı Sınıf Üstbilgisi (. H) Dosya

Circ denetimi için özellikleri almak ve ayarlamak (ve `CCirc` yöntemleri çağırmak) için sarıcı sınıfı, açığa çıkan tüm yöntem ve özelliklerin bir bildirimini sağlar. Örnekte, bu bildirimler CIRC bulunur. H. Aşağıdaki örnek, sınıfın `CCirc` ActiveX denetiminin açıkta kalan arabirimlerini tanımlayan bölümüdür:

[!code-cpp[NVC_MFC_AxCont#2](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_2.h)]
[!code-cpp[NVC_MFC_AxCont#3](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_3.h)]

Bu işlevler daha sonra normal C++ sözdizimi kullanılarak uygulamanın diğer yordamlarından çağrılabilir. Denetimin yöntemlerine ve özelliklerine erişmek için bu üye işlev kümesini kullanma hakkında daha fazla bilgi için [ActiveX denetimini programlama bölümüne](#_core_programming_the_activex_control)bakın.

## <a name="member-variable-modifications-to-the-project"></a><a name="_core_member_variable_modifications_to_the_project"></a>Projede Üye Değişken Değişiklikleri

ActiveX denetimi projeye eklendikten ve bir iletişim kutusu kapsayıcısına katıştırıldıktan sonra, projenin diğer bölümleri tarafından erişilebilir. Denetime erişmesinin en kolay yolu, `CContainerDlg` Visual C++tarafından projeye eklenen sarıcı sınıfıyla aynı türde olan iletişim sınıfının (adım 2) bir üye [değişkeni oluşturmaktır.](../mfc/activex-control-containers-connecting-an-activex-control-to-a-member-variable.md) Daha sonra, katıştılmış denetime istediğiniz zaman erişmek için üye değişkeni kullanabilirsiniz.

Üye **Değişken ekle** iletişim kutusu projeye *m_circctl* üye değişkeni eklediğinde, üstbilgi dosyasına aşağıdaki satırları da ekler (. H) `CContainerDlg` Sınıfın:

[!code-cpp[NVC_MFC_AxCont#4](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_4.h)]
[!code-cpp[NVC_MFC_AxCont#5](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_5.h)]

Buna ek olarak, **DDX_Control'a** yapılan `CContainerDlg`bir çağrı `DoDataExchange`otomatik olarak 'ın uygulamasına eklenir:

[!code-cpp[NVC_MFC_AxCont#6](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_6.cpp)]

## <a name="programming-the-activex-control"></a><a name="_core_programming_the_activex_control"></a>ActiveX Denetimini Programlama

Bu noktada, activex denetimini iletişim şablonunuza eklediniz ve bunun için bir üye değişken oluşturdunuz. Artık katıştılmış denetimin özelliklerine ve yöntemlerine erişmek için ortak C++ sözdizimini kullanabilirsiniz.

Belirtildiği gibi [(The Wrapper Class Header(. H) Dosya](#_core_the_wrapper_class_header_28h29_file)), üstbilgi dosyası (. H) `CCirc` sarma sınıfı için, bu durumda CIRC. H, herhangi bir açık özellik değerini almak ve ayarlamak için kullanabileceğiniz üye işlevlerin bir listesini içerir. Maruz kalan yöntemler için üye işlevler de mevcuttur.

Denetimin özelliklerini değiştirmek için ortak bir `OnInitDialog` yer ana iletişim sınıfının üye işlevindedir. Bu işlev, iletişim kutusu görünmeden hemen önce çağrılır ve denetimlerinden herhangi biri de dahil olmak üzere içeriğini başlatmaya kullanılır.

Aşağıdaki kod örneği, katıştirilen Circ denetiminin Resim Yazısı ve CircleShape özelliklerini değiştirmek için *m_circctl* üye değişkenini kullanır:

[!code-cpp[NVC_MFC_AxCont#7](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_7.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[ActiveX Kontrol Kapları](../mfc/activex-control-containers.md)
