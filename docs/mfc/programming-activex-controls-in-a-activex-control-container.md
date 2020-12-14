---
description: 'Daha fazla bilgi edinin: ActiveX denetim kapsayıcıları: ActiveX denetim kapsayıcısında ActiveX denetimlerini programlama'
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
ms.openlocfilehash: 34a5a2aaa1d7ec940ea31ae2fbe8c89ba3d84818
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97251017"
---
# <a name="activex-control-containers-programming-activex-controls-in-an-activex-control-container"></a>ActiveX Denetim Kapsayıcıları: Bir ActiveX Denetim Kapsayıcısındaki ActiveX Denetimlerini Programlama

Bu makalede, katıştırılmış ActiveX denetimlerinin sunulan [yöntemlerine](../mfc/mfc-activex-controls-methods.md) ve [özelliklerine](../mfc/mfc-activex-controls-properties.md) erişme süreci açıklanmaktadır.

>[!IMPORTANT]
> ActiveX, yeni geliştirme için kullanılması gereken eski bir teknolojidir. ActiveX 'in yerini alan modern teknolojiler hakkında daha fazla bilgi için bkz. [ActiveX denetimleri](activex-controls.md).

Temel olarak şu adımları izleyeceğinizi göreceksiniz:

1. Galeri kullanarak [ActiveX kapsayıcısı projesine ActiveX denetimi ekleyin](../mfc/inserting-a-control-into-a-control-container-application.md) .

1. ActiveX denetim sarmalayıcı sınıfıyla aynı türde [bir üye değişkeni](../mfc/activex-control-containers-connecting-an-activex-control-to-a-member-variable.md) (veya başka bir erişim biçimi) tanımlayın.

1. Sarmalayıcı sınıfının önceden tanımlanmış üye işlevlerini kullanarak [ActiveX denetimini programlayabilirsiniz](#_core_programming_the_activex_control) .

Bu tartışma için, ActiveX denetim desteğiyle bir iletişim temelli proje (kapsayıcı adı) oluşturduğunuzu varsayalım. Circ örnek denetimi, Circ, sonuçta elde edilen projeye eklenecektir.

Circ denetimi projeye eklendikten sonra (1. adım), Circ denetiminin bir örneğini uygulamanın ana iletişim kutusuna ekleyin.

## <a name="procedures"></a>Yordamlar

#### <a name="to-add-the-circ-control-to-the-dialog-template"></a>İletişim kutusu şablonuna Circ denetimini eklemek için

1. ActiveX Denetim kapsayıcısı projesini yükleyin. Bu örnek için, projeyi kullanın `Container` .

1. Kaynak Görünümü sekmesine tıklayın.

1. **Iletişim kutusu** klasörünü açın.

1. Ana iletişim kutusu şablonuna çift tıklayın. Bu örnek için **IDD_CONTAINER_DIALOG** kullanın.

1. Araç kutusundaki Circ denetimi simgesine tıklayın.

1. Circ denetimini eklemek için iletişim kutusu içindeki bir noktaya tıklayın.

1. Tüm değişiklikleri iletişim kutusu şablonuna kaydetmek için **Dosya** menüsünde **Tümünü Kaydet** ' i seçin.

## <a name="modifications-to-the-project"></a>Projede yapılan değişiklikler

Kapsayıcı uygulamasının Circ denetimine erişmesini sağlamak için, Visual C++ sarmalayıcı sınıf ( `CCirc` ) uygulama dosyasını (. CPP) kapsayıcı projesine ve sarmalayıcı sınıf başlığına (. H) dosyayı iletişim kutusu üstbilgi dosyasına:

[!code-cpp[NVC_MFC_AxCont#1](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_1.h)]

## <a name="the-wrapper-class-header-h-file"></a><a name="_core_the_wrapper_class_header_28h29_file"></a> Sarmalayıcı sınıf üst bilgisi (. H) dosyası

Circ denetimi için özellikleri almak ve ayarlamak (ve yöntemleri çağırmak) için `CCirc` sarmalayıcı sınıfı, sunulan tüm yöntemlerin ve özelliklerin bir bildirimini sağlar. Örnekte, bu bildirimler CIRC. H içinde bulunur. Aşağıdaki örnek, `CCirc` ActiveX denetiminin sunulma arabirimlerini tanımlayan sınıfının bölümüdür:

[!code-cpp[NVC_MFC_AxCont#2](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_2.h)]
[!code-cpp[NVC_MFC_AxCont#3](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_3.h)]

Bu işlevler daha sonra, normal C++ sözdizimi kullanılarak uygulamanın yordamlarından çağrılabilir. Bu üye işlev kümesini denetimin yöntemlerine ve özelliklerine erişmek üzere kullanma hakkında daha fazla bilgi için, [ActiveX denetimini programlama](#_core_programming_the_activex_control)bölümüne bakın.

## <a name="member-variable-modifications-to-the-project"></a><a name="_core_member_variable_modifications_to_the_project"></a> Projede üye değişkeni değişiklikleri

ActiveX denetimi projeye eklendikten ve iletişim kutusu kapsayıcısına katıştırıldıktan sonra, projenin diğer bölümleri tarafından erişilebilir. Denetime erişmenin en kolay yolu, [](../mfc/activex-control-containers-connecting-an-activex-control-to-a-member-variable.md) `CContainerDlg` Visual C++ tarafından projeye eklenen sarmalayıcı sınıfıyla aynı türde olan (2. adım) iletişim kutusu sınıfının bir üye değişkenini oluşturmaktır. Daha sonra istediğiniz zaman katıştırılmış denetime erişmek için üye değişkenini kullanabilirsiniz.

**Üye değişkeni Ekle** iletişim kutusu projeye *m_circctl* üye değişkenini eklediğinde, başlık dosyasına da aşağıdaki satırları ekler (. H) `CContainerDlg` sınıfının:

[!code-cpp[NVC_MFC_AxCont#4](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_4.h)]
[!code-cpp[NVC_MFC_AxCont#5](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_5.h)]

Ayrıca, bir **DDX_Control** çağrısı, öğesinin uygulamasına otomatik olarak eklenir `CContainerDlg` `DoDataExchange` :

[!code-cpp[NVC_MFC_AxCont#6](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_6.cpp)]

## <a name="programming-the-activex-control"></a><a name="_core_programming_the_activex_control"></a> ActiveX denetimini programlama

Bu noktada, ActiveX denetimini iletişim uygulamanıza eklediniz ve onun için bir üye değişkeni oluşturdunuz. Artık katıştırılmış denetimin özelliklerine ve yöntemlerine erişmek için ortak C++ söz dizimini kullanabilirsiniz.

Belirtildiği gibi ( [sarmalayıcı sınıfı üst bilgisinde (. H) dosyası](#_core_the_wrapper_class_header_28h29_file)), üst bilgi dosyası (. H) `CCirc` sarmalayıcı sınıfı için, bu durumda CIRC. H, sunulan herhangi bir özellik değerini almak ve ayarlamak için kullanabileceğiniz üye işlevlerinin bir listesini içerir. Sunulan yöntemlerin üye işlevleri de mevcuttur.

Denetimin özelliklerini değiştirmek için ortak bir yer, `OnInitDialog` ana iletişim sınıfının üye işlevidir. Bu işlev, iletişim kutusu görüntülenmeden hemen önce çağrılır ve onun denetimleri dahil olmak üzere içeriğini başlatmak için kullanılır.

Aşağıdaki kod örneği, gömülü Circ denetiminin başlık ve CircleShape özelliklerini değiştirmek için *m_circctl* member değişkenini kullanır:

[!code-cpp[NVC_MFC_AxCont#7](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_7.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[ActiveX denetim kapsayıcıları](../mfc/activex-control-containers.md)
