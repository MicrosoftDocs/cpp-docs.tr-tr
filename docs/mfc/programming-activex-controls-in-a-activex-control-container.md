---
title: 'ActiveX denetim kapsayıcıları: Bir ActiveX denetim kapsayıcısındaki ActiveX denetimlerini programlama | Microsoft Docs'
ms.custom: ''
ms.date: 09/12/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f68e74c5374379019fd8fd5b0348b34e36005171
ms.sourcegitcommit: b4432d30f255f0cb58dce69cbc8cbcb9d44bc68b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/13/2018
ms.locfileid: "45535333"
---
# <a name="activex-control-containers-programming-activex-controls-in-an-activex-control-container"></a>ActiveX Denetim Kapsayıcıları: Bir ActiveX Denetim Kapsayıcısındaki ActiveX Denetimlerini Programlama
Bu makalede gösterilen erişme işlemi [yöntemleri](../mfc/mfc-activex-controls-methods.md) ve [özellikleri](../mfc/mfc-activex-controls-properties.md) katıştırılmış ActiveX denetimi. 

>[!IMPORTANT]
> ActiveX yeni geliştirme projeleri için kullanılmaması gereken eski bir teknolojidir. ActiveX yerini modern teknolojiler hakkında daha fazla bilgi için bkz. [ActiveX denetimlerini](activex-controls.md).

Temel olarak, aşağıdaki adımları izler:  
  
1.  [Bir ActiveX denetimini ActiveX kapsayıcı projeye ekleyin](../mfc/inserting-a-control-into-a-control-container-application.md) galerisini kullanarak.  
  
2.  [Üye değişkeni tanımlamak](../mfc/activex-control-containers-connecting-an-activex-control-to-a-member-variable.md) (veya başka bir form erişim) aynı tür olarak ActiveX denetimi sarmalayıcı sınıfı.  
  
3.  [ActiveX denetimi program](#_core_programming_the_activex_control) önceden tanımlanmış sarmalayıcı sınıfın üye işlevleri kullanarak.  
  
 Bu tartışma için ActiveX denetimi desteği (kapsayıcı olarak adlandırılır) ve iletişim tabanlı bir proje oluşturdunuz varsayılır. Dai örnek denetimi Dai, sonuçta elde edilen projeye eklenir.  
  
 (1. adım) projeye Dai denetimi ekledikten sonra Dai denetim örneği uygulamanın ana iletişim kutusuna yerleştirin.  
  
## <a name="procedures"></a>Yordamlar  
  
#### <a name="to-add-the-circ-control-to-the-dialog-template"></a>İletişim şablona Dai denetimi eklemek için  
  
1.  ActiveX denetimi kapsayıcısı projesine yükleyin. Bu örneğin `Container` proje.  
  
2.  Kaynak Görünümü sekmesine tıklayın.  
  
3.  Açık **iletişim** klasör.  
  
4.  Ana iletişim kutusu şablonu çift tıklayın. Bu örneğin **IDD_CONTAINER_DIALOG**.  
  
5.  Araç kutusu Dai denetim simgesine tıklayın.  
  
6.  Bir nokta Dai denetim eklemek için iletişim kutusuna tıklayın.  
  
7.  Gelen **dosya** menüsünde seçin **Tümünü Kaydet** iletişim kutusunda şablon için tüm değişiklikleri kaydedin.  
  
## <a name="modifications-to-the-project"></a>Proje yapılan değişiklikler  
 Kapsayıcı uygulamanın erişim Dai denetimi etkinleştirmek için Visual C++ otomatik olarak sarmalayıcı sınıfı ekler (`CCirc`) uygulama dosyası (. CPP) kapsayıcı proje ile sarmalayıcı sınıfı üst bilgisi (. H) dosyası için iletişim kutusunun üst bilgi dosyası:  
  
 [!code-cpp[NVC_MFC_AxCont#1](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_1.h)]  
  
##  <a name="_core_the_wrapper_class_header_28h29_file"></a> Sarmalayıcı sınıf üst bilgisi (. H) dosyası  
 Almak ve özelliklerini ayarlayın (ve yöntemlerini çağırmak için) Dai denetimi için `CCirc` sarmalayıcı sınıfı bildirimi kullanıma sunulan tüm yöntemleri ve özellikleri sağlar. Örnekte, bu bildirimleri CIRC. içinde bulunur. H Aşağıdaki örnek sınıf bölümüdür `CCirc` , arabirimleri ActiveX denetiminin tanımlar:  
  
 [!code-cpp[NVC_MFC_AxCont#2](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_2.h)]  
[!code-cpp[NVC_MFC_AxCont#3](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_3.h)]  
  
 Bu işlevler ardından diğer uygulamanın yordamları normal bir C++ sözdizimi kullanılarak çağrılabilir. Denetimin yöntemlere ve özelliklere erişmek için bu üye işlevini kullanma hakkında daha fazla bilgi için bkz [ActiveX denetimini programlama](#_core_programming_the_activex_control).  
  
##  <a name="_core_member_variable_modifications_to_the_project"></a> Üye değişkeni değişiklikleri projeye  
 ActiveX denetimi projeye eklenir ve bir iletişim kutusu kapsayıcıda katıştırılmış sonra projenin diğer bölümlerinde tarafından erişilebilir. Erişim denetimi için en kolay yolu [bir üye değişkeni oluşturma](../mfc/activex-control-containers-connecting-an-activex-control-to-a-member-variable.md) iletişim sınıfının `CContainerDlg` (, yani adım 2) Visual C++ tarafından projeye eklenen sarmalayıcı sınıfı ile aynı türde. Ardından, katıştırılmış denetime herhangi bir zamanda erişmek için üye değişkeni kullanabilirsiniz.  
  
 Zaman **üye değişkeni ekleme** iletişim kutusu ekler *m_circctl* üye değişkeni projeye de aşağıdaki satırları üstbilgi dosyasına ekler (. H), `CContainerDlg` sınıfı:  
  
 [!code-cpp[NVC_MFC_AxCont#4](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_4.h)]  
[!code-cpp[NVC_MFC_AxCont#5](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_5.h)]  
  
 Ayrıca, bir çağrı **DDX_Control** otomatik olarak eklenir `CContainerDlg`'s uygulaması `DoDataExchange`:  
  
 [!code-cpp[NVC_MFC_AxCont#6](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_6.cpp)]  
  
##  <a name="_core_programming_the_activex_control"></a> ActiveX denetimi programlama  
 Bu noktada, iletişim şablonunuza ActiveX denetimi eklenir ve bir üye değişkeni oluşturulduğu. Artık, özellikleri ve yöntemleri gömülü denetimin erişmek için ortak C++ söz dizimini kullanabilirsiniz.  
  
 Belirtildiği gibi (içinde [sarmalayıcı sınıfı üst bilgisi (. H) dosya](#_core_the_wrapper_class_header_28h29_file)), üst bilgi dosyası (. H) için `CCirc` bu büyük/küçük harf CIRC. içinde sarmalayıcı sınıfı H, almak ve herhangi bir kullanıma sunulan bir özelliğin değerini ayarlamak için kullanabileceğiniz üye işlevlerin listesini içerir. Üye işlevleri için kullanıma sunulan yöntemleri de mevcuttur.  
  
 Denetimin özelliklerini değiştirmek için ortak bir konum `OnInitDialog` ana iletişim sınıfının üye işlevi. Yeni iletişim kutusu görünür ve içerikleri denetimlerinden birini de dahil olmak üzere, başlatmak için kullanılan önce bu işlev çağrılır.  
  
 Aşağıdaki kod örneğinde *m_circctl* üye değişkeni, eklenen Dai denetimin açıklamalı alt yazı ve CircleShape özelliklerini değiştirmek için:  
  
 [!code-cpp[NVC_MFC_AxCont#7](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_7.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ActiveX Denetim Kapsayıcıları](../mfc/activex-control-containers.md)

