---
title: Menü komut özellikleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- menu items, properties
ms.assetid: 6d308205-3c9e-42f2-ab42-45e656940e45
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 34fa9944d1daa443850454560f8e5741e881f6f8
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42598717"
---
# <a name="menu-command-properties"></a>Menü Komut Özellikleri

Aşağıdaki bilgilere göre düzenlenmiş **menü** görünen Özellikler [Özellikler penceresi](/visualstudio/ide/reference/properties-window) seçtiğinizde bir menü komutu. Bu rağmen alfabetik olarak listelenen **özellikleri** pencere Ayrıca bu özellikleri kategoriye göre görüntüle olanak sağlar.

|Özellik|Açıklama|
|--------------|-----------------|
|**sonu**|Şu değerlerden biri olabilir:<br /><br /> -   **Hiçbiri** (varsayılan): kesme yok.<br />-   **Sütun**: statik menüleri için bu değer menü komutu yeni bir satıra yerleştirir. Açılır menüler için bu değeri hiçbir sütunları arasındaki çizgi ile yeni bir sütun menü komutunu yerleştirir. Bu özelliğin ayarlanması menü görünümünü yalnızca çalışma zamanında, menü Düzenleyicisi'nde etkiler.<br />-   **Çubuk**: aynı **sütun** dışında açılır menüler için bu değeri yeni bir sütun içeren bir dikey çizgi eski sütunu ayırır. Bu özelliğin ayarlanması etkiler menü görünümünü yalnızca çalışma zamanında değil **menü** Düzenleyici.|
|**Resim yazısı**|Menü komutunu (menü adı) etiket metni. Bir harf menüsünün açıklamasındaki kısayol tuşu komutu, bir ampersan ile önünde olmak için (&).|
|**İşaretli**|Varsa **True**, menü komutunu başlangıçta denetlenir. Türü: **Bool**. Varsayılan: **False**.|
|**Etkin**|Varsa **False**, menü öğesi devre dışı bırakıldı.|
|**Gri**|Varsa **True**, başlangıçta gri ve etkin olmayan menü komutu. Türü: **Bool**. Varsayılan: **False**.|
|**Yardım**|Menü öğesi sağa hizalar. Örneğin, **yardımcı** menü komutu olduğundan her zaman, tüm Windows uygulamalarını sağdaki. Bir menü öğesi bu özelliği ayarlarsanız, bu öğe en çok sağdaki ve menüsünün en sonunda görünür. Üst düzey öğeleri için geçerlidir. Varsayılan: **False**.|
|**ID**|Üst bilgi dosyasında tanımlanan bir simge. Türü: **sembol**, **tamsayı**, veya **sınırlandırılmış**. Yaygın olarak kullanılabilen düzenleyicileri hiçbirinde olsa bile herhangi bir simge kullanabilir [Özellikler penceresi](/visualstudio/ide/reference/properties-window) arasından seçim yapabileceğiniz bir açılan liste sağlamaz.|
|**Açılan Pencere**|Varsa **True**, açılır menü menü komutudur. Türü: **Bool**. Varsayılan: **True** için menü çubuğundan; Aksi halde üst düzey menülere **False**.|
|**istemi**|Bu menü komutu vurgulandığında durum çubuğunda görüntülenecek metni içerir. Menü komutu ile aynı tanımlayıcıyla dize tablosunda metin yerleştirilir. Bu özellik, her türden proje için kullanılabilir, ancak MFC belirli çalışma zamanı işlevdir.|
|**Sağdan Sola Yasla**|Sağa hizalar çalışma zamanında menü çubuğundaki menü komutu. Türü: **Bool**. Varsayılan: **False**.|
|**Sağa sola düzeni için**|Sağ İbranice ve Arapça gibi sola, okuyan herhangi bir dil için yerelleştirilmiş arabirim sağdan sola görüntülemek, menü komutlarını sağlar.|
|**Ayıraç**|Varsa **True**, menü komutunu olduğu bir ayırıcı. Türü: **Bool**. Varsayılan: **False**.|

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[Menü Düzenleyicisi](../windows/menu-editor.md)