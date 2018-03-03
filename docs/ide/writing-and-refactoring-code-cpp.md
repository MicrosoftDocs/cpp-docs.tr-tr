---
title: "Yazma ve kod (C++) yeniden düzenlemesi | Microsoft Docs"
ms.custom: 
ms.date: 11/27/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 56ffb9e9-514f-41f4-a3cf-fd9ce2daf3b6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b68d4190d8e3fc5040879eba4f8888467a07adf5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="writing-and-refactoring-code-c"></a>Yazma ve yeniden düzenleme kod (C++)

Visual C++ kod düzenleyicisini ve IDE birçok kodlama yardımları sağlar. Bazı C++ için benzersiz ve bazı temelde tüm Visual Studio diller için aynıdır. Paylaşılan özellikler hakkında daha fazla bilgi için bkz: [kod ve Metin Düzenleyici'de kod yazma](/visualstudio/ide/writing-code-in-the-code-and-text-editor). Etkinleştirme ve C++ özgü özellikleri yapılandırmak için seçenekleri bulunur [metin düzenleyici C++ Gelişmiş](/visualstudio/ide/reference/options-text-editor-c-cpp-advanced) iletişim (**Araçları &#124; Seçenekler &#124; Metin Düzenleyici &#124; C/C++ &#124; Gelişmiş** veya yazın "C++ Gelişmiş" **hızlı başlatma**). Ayarlamak istediğiniz hangi seçeneği seçtikten sonra daha fazla yardım tuşlarına basarak alabilirsiniz **F1** iletişim odakta olduğunda. Biçimlendirme seçeneklerini genel kodunu yazın `Editor C++` içine **Hızlı Başlat**.

İçinde bulunan olabilir veya Visual Studio, gelecekteki bir sürümüne dahil edilmeyen Deneysel özellikleri [metin düzenleyici C++ Experimental](/visualstudio/ide/reference/options-text-editor-c-cpp-experimental) iletişim. Visual Studio 2017 içinde etkinleştirmeniz **Tahmine dayalı IntelliSense** bu iletişim.

## <a name="adding-new-code"></a>Yeni kod ekleme

Bir proje oluşturduktan sonra sizin için oluşturulan dosyalarında kodlama başlatabilirsiniz. Yeni dosya eklemek için Çözüm Gezgini'nde proje düğümüne sağ tıklayın ve seçin **Ekle &#124; Yeni**.

Biçimlendirme girintileri, küme parantezi tamamlama ve renklendirme gibi seçenekleri ayarlamak için şunu yazın `C++ Formatting` içine **Hızlı Başlat** penceresi.

### <a name="intellisense"></a>IntelliSense

IntelliSense üyeleri, türleri ve işlev aşırı yüklemelerinin hakkında satır içi bilgi sağlayan özellikleri kümesi adıdır. Aşağıdaki çizimde yazarken görüntülenen üye listesi açılır gösterir. Seçili öğeyi metin kodu dosyanıza girmek için SEKME tuşuna basabilirsiniz.

![C# 43; &#43; üye listesi açılır](../ide/media/vs2015_cpp_statement_completion.png "vs2015_cpp_statement_completion")

Tam bilgi için bkz: [Visual C++ IntelliSense](/visualstudio/ide/visual-cpp-intellisense).

### <a name="insert-snippets"></a>Kod parçacıkları Ekle

Bir kod parçacığında, kaynak kodu önceden tanımlanmış bir parçasıdır. Tek bir nokta ya da bir parçacığını eklemek ya da kod parçacığını seçili metinle surround için seçili metnin sağ tıklayın. Seçili deyimiyle surround için üç adım aşağıda gösterilmiştir bir döngü için. Son görüntüde sarı vurgular SEKME tuşu ile erişim düzenlenebilir alanlardır. Daha fazla bilgi için bkz: [kod parçacıkları](/visualstudio/ide/code-snippets).

![Visual C# 43; &#43; Kod parçacığında bırak &#45;Ekle; aşağı](../ide/media/vs2015_cpp_surround_with.png "vs2015_cpp_surround_with")

### <a name="add-class"></a>Sınıf ekleme

Yeni bir sınıf ekleyin **proje** sınıfı Sihirbazı'nı kullanarak menüsü.

![Visual C# 43; &#43;içinde yeni sınıf ekleyin; ] (../ide/media/vs2015_cpp_add_class.png "vs2015_cpp_add_class")

### <a name="class-wizard"></a>Sınıf Sihirbazı

Değiştirin veya varolan bir sınıfa inceleyin veya sınıfı Sihirbazı'nı kullanarak yeni bir sınıf ekleyin. Daha fazla bilgi için bkz: [işlevsellik ekleme kodu sihirbazlar (C++) ile](../ide/adding-functionality-with-code-wizards-cpp.md).

![Visual C# 43; &#43; Sınıf Sihirbazı](../ide/media/vs2015_cpp_class_wizard.png "vs2015_cpp_class_wizard")

## <a name="refactoring"></a>Yeniden Düzenle

Yapan yeniden düzenlemeler hızlı eylem bağlam menüsü altında veya tıklayarak mevcut bir [ampul](/visualstudio/ide/perform-quick-actions-with-light-bulbs) Düzenleyicisi'nde.  Bazı de bulunan **Düzenle > yeniden düzenlemeniz** menüsü.  Bu özellikler şunlardır:

* [Yeniden Adlandır](refactoring/rename.md)
* [İşlevi Ayıkla](refactoring/extract-function.md)
* [Saf Sanalları Uygula](refactoring/implement-pure-virtuals.md)
* [Bildirim / Tanım Oluştur](refactoring/create-declaration-definition.md)
* [Move İşleminin Tanımı](refactoring/move-definition-location.md)
* [Ham Dize Sabit Değerine Dönüştür](refactoring/convert-to-raw-string-literal.md)
* [İmzayı Değiştir](refactoring/change-signature.md)

## <a name="navigate-and-understand"></a>Gidin ve anlama

Visual C++ kodu Gezinti özelliklerinin diğer dilleri ile paylaşır. Daha fazla bilgi için bkz: [gezinme kodu](/visualstudio/ide/navigating-code) ve [kodunu yapısı görüntüleme](/visualstudio/ide/viewing-the-structure-of-code).

### <a name="quickinfo"></a>Quıckınfo

Tür bilgilerini görmek için bir değişken gelin.

![Visual C# 43; &#43; Quıckınfo](../ide/media/vs2015_cpp_quickinfo.png "vs2015_cpp_quickInfo")

### <a name="open-document-navigate-to-header"></a>Açık belge (üstbilgi Git)

Üstbilgi adını sağ tıklayın bir `#include` yönergesi ve üst bilgi dosyasını açın.

![Visual C# 43; &#43; Belge menü seçeneğini açın](../ide/media/vs2015_cpp_open_document.png "vs2015_cpp_open_document")

### <a name="peek-definition"></a>Özet tanımı

Bir değişken veya işlev bildirimi, sağ tıklatın, sonra vurgulu seçin **Peek tanımı** tanımına satır içi görünümünü görmek için. Daha fazla bilgi için bkz: [Peek tanımı (Alt + F12)](/visualstudio/ide/how-to-view-and-edit-code-by-using-peek-definition-alt-plus-f12).

![Visual C# 43; &#43; Tanım Ara](../ide/media/vs2015_cpp_peek_definition.png "vs2015_cpp_peek_definition")

### <a name="go-to-definition"></a>Tanıma gitme

Bir değişken veya işlev bildirimi, sağ tıklatın, sonra vurgulu seçin **Tanıma Git** nesne tanımlandığı belgeyi açmak için.

### <a name="view-call-hierarchy"></a>Çağrı hiyerarşisini görüntüleme

Herhangi bir işlev çağrısına sağ tıklayın ve çağırır tüm işlevleri ve bunu tüm işlevleri resursive listesini görüntüleyin. Listedeki her işlevi aynı şekilde genişletilebilir. Daha fazla bilgi için bkz: [çağrı hiyerarşisi](/visualstudio/ide/reference/call-hierarchy).

![Visual C# 43; &#43; Çağrı hiyerarşisi](../ide/media/vs2015_cpp_call_hierarchy.png "vs2015_cpp_call_hierarchy")

### <a name="toggle-header--code-file"></a>Geçiş üstbilgi / kod dosyası

Sağ tıklatın ve seçin **geçiş üstbilgi / kod dosyası** geri ve İleri üstbilgi dosyası ve onun ilişkili kod dosyası arasında geçiş yapmak için.

### <a name="outlining"></a>Anahat Oluşturma

Herhangi bir kaynak kodu dosyasına sağ tıklayın ve seçin **anahat** daraltın veya tanımları ve/veya yalnızca ilgilendiğiniz bölümleri Gözat kolaylaştırmak için özel bölgeler genişletin. Daha fazla bilgi için bkz: [anahat](/visualstudio/ide/outlining).

![Visual C# 43; &#43; Anahat oluşturma](../ide/media/vs2015_cpp_outlining.png "vs2015_cpp_outlining")

### <a name="scroll-bar-map-mode"></a>Kaydırma çubuğu eşleme modu

ScrollBar eşleme modu, hızla kaydırın ve kod dosyası aracılığıyla geçerli konumunuz ayrılmadan Gözat olanak sağlar. Veya bu konuma doğrudan gitmek için kod Haritası herhangi bir yere tıklayın.

![Kod Haritası Visual C &#43; &#43; ] (../ide/media/vs2015_cpp_code_map.png "vs2015_cpp_code_map")

### <a name="generate-graph-of-include-files"></a>Dosyaları Ekle Grafiği Oluştur

Bir kod dosyası projenize sağ tıklayın ve seçin **dosyaları Ekle Generate grafiği** hangisinin dosyaları diğer dosyalar tarafından eklenir bir grafik görmek için.

![Visual C# 43; &#43; Dosyaları Ekle grafiği](../ide/media/vs2015_cpp_include_graph.png "vs2015_cpp_include_graph")

### <a name="f1-help"></a>F1 Yardımı

İmleç üzerinde veya herhangi bir tür, anahtar sözcüğü veya işlevi hemen sonra yerleştirin ve ilgili MSDN başvuru konuya doğrudan gitmek için F1 tuşuna basın. F1 hata listesinde ve birçok iletişim kutularındaki öğeler üzerinde de çalışır.

### <a name="quick-launch"></a>Hızlı Başlat

Kolayca herhangi bir pencere veya Visual Studio aracında gitmek için yalnızca kullanıcı arabirimini sağ üst köşesindeki hızlı başlatma penceresinde adını yazın. Siz yazarken otomatik tamamlama listesini filtreler.

![Visual Studio hızlı başlatma](../ide/media/vs2015_cpp_quick_launch.png "vs2015_cpp_quick_launch")
