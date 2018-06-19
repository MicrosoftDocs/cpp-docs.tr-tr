---
title: 'ActiveX denetim kapsayıcıları: Bir ActiveX denetim kapsayıcısındaki ActiveX denetimlerini programlama | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: bae926cfc7e83edeef9ee68c7ce7118c55009a08
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33355047"
---
# <a name="activex-control-containers-programming-activex-controls-in-an-activex-control-container"></a>ActiveX Denetim Kapsayıcıları: Bir ActiveX Denetim Kapsayıcısındaki ActiveX Denetimlerini Programlama
Bu makalede gösterilen erişmek için işlem [yöntemleri](../mfc/mfc-activex-controls-methods.md) ve [özellikleri](../mfc/mfc-activex-controls-properties.md) katıştırılmış ActiveX denetimlerinin. Temel olarak, şu adımları izler:  
  
1.  [Bir ActiveX denetimini ActiveX kapsayıcı projeye ekleyin](../mfc/inserting-a-control-into-a-control-container-application.md) Galeri'yi kullanma.  
  
2.  [Üye değişkeni tanımlamanız](../mfc/activex-control-containers-connecting-an-activex-control-to-a-member-variable.md) (veya başka bir form erişim) ActiveX aynı türde denetim sarmalayıcı sınıfı.  
  
3.  [ActiveX denetimi program](#_core_programming_the_activex_control) önceden tanımlanmış sarmalayıcı sınıfı üye işlevlerini kullanarak.  
  
 Bu tartışma için (kapsayıcı adlı) iletişim tabanlı projesi oluşturmuş olduğunuz ActiveX denetimi desteğiyle varsayalım. Dai örnek denetimi Dai, sonuçta elde edilen projeye eklenir.  
  
 Dai denetimi (1. adım) projeye eklendiğinde Dai denetim örneği uygulamanın ana iletişim kutusuna ekleyin.  
  
## <a name="procedures"></a>Yordamlar  
  
#### <a name="to-add-the-circ-control-to-the-dialog-template"></a>Dai denetimi iletişim şablona eklemek için  
  
1.  ActiveX denetimi kapsayıcısı projesine yükleyin. Bu örneğin `Container` projesi.  
  
2.  Kaynak Görünümü sekmesini tıklatın.  
  
3.  Açık **iletişim** klasör.  
  
4.  Ana iletişim kutusu şablonu çift tıklatın. Bu örneğin **IDD_CONTAINER_DIALOG**.  
  
5.  Araç çubuğundaki Dai denetim simgesini tıklatın.  
  
6.  Dai denetim eklemek için iletişim kutusu içinde bir noktaya tıklayın.  
  
7.  Gelen **dosya** menüsünde seçin **Tümünü Kaydet** iletişim kutusuna şablon için tüm değişiklikleri kaydetmek için.  
  
## <a name="modifications-to-the-project"></a>Proje yapılan değişiklikler  
 Kapsayıcı uygulamanın erişim Dai denetimi etkinleştirmek için Visual C++ otomatik olarak sarmalayıcı sınıfı ekler (`CCirc`) uygulama dosyasını (. CPP) kapsayıcı proje ve sarmalayıcı sınıfı üstbilgi (. H) iletişim kutusu üstbilgi dosyası dosyasına:  
  
 [!code-cpp[NVC_MFC_AxCont#1](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_1.h)]  
  
##  <a name="_core_the_wrapper_class_header_28h29_file"></a> Sarmalayıcı sınıfı üstbilgi (. H) dosyası  
 Almak ve özelliklerini ayarlayın (ve yöntemleri çağırmak için) Dai denetiminin `CCirc` sarmalayıcı sınıfı, bir bildirimi tüm sunulan yöntemleri ve özellikleri sağlar. Örnekte, bu bildirimleri CIRC. içinde bulunan H. Aşağıdaki örnek sınıf bölümüdür. `CCirc` arabirimleri ActiveX denetiminin tanımlar:  
  
 [!code-cpp[NVC_MFC_AxCont#2](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_2.h)]  
[!code-cpp[NVC_MFC_AxCont#3](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_3.h)]  
  
 Bu işlevler, ardından diğer normal C++ söz dizimini kullanarak uygulamanın yordamları çağrılabilir. Denetimin yöntemleri ve özellikleri erişmek için bu üye işlevini kullanma hakkında daha fazla bilgi için bkz [ActiveX denetimini programlama](#_core_programming_the_activex_control).  
  
##  <a name="_core_member_variable_modifications_to_the_project"></a> Projenin üye değişken değişiklikler  
 ActiveX denetimi projeye eklenir ve bir iletişim kutusu kapsayıcısında katıştırılmış sonra projeyi diğer bölümleri tarafından erişilebilir. Erişim denetimi için en kolay yolu [üye değişkeni oluşturma](../mfc/activex-control-containers-connecting-an-activex-control-to-a-member-variable.md) iletişim sınıfının `CContainerDlg` (2, yani adım) tarafından Visual C++ projeye eklenen sarmalayıcı sınıf ile aynı türde. Üye değişkeni sonra herhangi bir zamanda katıştırılmış denetime erişmek için de kullanabilirsiniz.  
  
 Zaman **üye değişkeni ekleme** iletişim kutusu ekler `m_circctl` üye değişkeni projeye, ayrıca aşağıdaki satırları üstbilgi dosyası ekler (. H), `CContainerDlg` sınıfı:  
  
 [!code-cpp[NVC_MFC_AxCont#4](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_4.h)]  
[!code-cpp[NVC_MFC_AxCont#5](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_5.h)]  
  
 Ayrıca, bir çağrı **DDX_Control** otomatik olarak eklenen `CContainerDlg`'s uyarlamasını `DoDataExchange`:  
  
 [!code-cpp[NVC_MFC_AxCont#6](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_6.cpp)]  
  
##  <a name="_core_programming_the_activex_control"></a> ActiveX denetimi programlama  
 Bu noktada, iletişim şablonunuza ActiveX denetimini eklenen sahip ve bir üye değişkeni için oluşturulmuş. Artık, özellikleri ve yöntemleri katıştırılmış denetiminin erişmek için ortak C++ söz dizimini kullanabilirsiniz.  
  
 Belirtildiği gibi (içinde [sarmalayıcı sınıfı üstbilgi (. H) dosya](#_core_the_wrapper_class_header_28h29_file)), üst bilgi dosyasını (. H) için `CCirc` içindeki case bu CIRC. sarmalayıcı sınıfı H alın ve tüm açık özellik değerini ayarlamak için kullanabileceğiniz üye işlevleri listesini içerir. Üye işlevleri kullanıma sunulan yöntemleri için de kullanılabilir.  
  
 Denetimin özelliklerini değiştirmek için ortak bir yerde bulunduğu `OnInitDialog` ana iletişim sınıfının üye işlevi. Bu işlev yalnızca iletişim kutusu belirir ve denetimlerinden birini de dahil olmak üzere içeriğinin başlatmak için kullanılan önce çağrılır.  
  
 Aşağıdaki kod örneğinde `m_circctl` üye değişkeni katıştırılmış Dai denetim başlık ve CircleShape özelliklerini değiştirmek için:  
  
 [!code-cpp[NVC_MFC_AxCont#7](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_7.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ActiveX Denetim Kapsayıcıları](../mfc/activex-control-containers.md)

