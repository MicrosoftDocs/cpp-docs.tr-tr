---
title: Kapsam ve Görünürlük
ms.date: 11/04/2016
helpviewer_keywords:
- scope, levels
- visibility
- file scope [C++]
ms.assetid: a019eb7c-66ed-46a7-bc9f-89a963930a56
ms.openlocfilehash: 01b2bc8d75c3c65639a3ff0c57b1a368760eba53
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62158351"
---
# <a name="scope-and-visibility"></a>Kapsam ve Görünürlük

Bir tanımlayıcının "görünürlük", başvurubileceği programın ("kapsam") bölümlerini belirler. Bir tanımlayıcı görünür (yani, kullanılabilir) yalnızca "kapsamı" ile dahil olan bir programın bölümlerinde, sınırlı olabilen dosya, işlev, blok veya işlev prototipini ile sınırlı olabilecek (artan kısıtlayıcı bir şekilde) olabilir. Bir tanımlayıcının kapsamı, programın adının kullanılabileceği bölümüdür. Buna bazen "sözcük temelli kapsam" adı verilir. Dört tür kapsam vardır: işlev, dosya, blok ve işlev prototipi.

Etiketler hariç tüm tanımlayıcıların kapsamı, bildirimin gerçekleştiği düzeye göre belirlenir. Her bir kapsam türü için aşağıdaki kurallar, bir program içindeki tanımlayıcıların görünürlüğünü yönetir:

Dosya kapsamı dosya kapsamına sahip bir tanımlayıcı için bildirimci veya tür Belirleyicisi, herhangi bir blok veya parametre listesi dışında görünür ve bildiriminden sonra çeviri biriminde herhangi bir yerden erişilebilir olur. Dosya kapsamına sahip tanımlayıcı adları genellikle "Global" veya "External" olarak adlandırılır. Genel tanımlayıcının kapsamı, tanım veya bildiriminin başlangıcında başlar ve çeviri biriminin sonunda sonlanır.

İşlev kapsamı bir etiket işlev kapsamına sahip tek tanımlayıcı türüdür. Bir etiket, bir ifadede kullanımı tarafından örtük olarak bildirilmiştir. Etiket adları bir işlev içinde benzersiz olmalıdır. (Etiketler ve etiket adları hakkında daha fazla bilgi için bkz. [goto ve etiketli deyimler](../c-language/goto-and-labeled-statements-c.md).)

Blok kapsamı blok kapsamına sahip bir tanımlayıcı için bildirimci veya tür Belirleyicisi, bir blok içinde veya bir işlev tanımında biçimsel parametre bildirimleri listesi içinde görüntülenir. Yalnızca kendi bildirimi veya tanımı, bildirimini veya tanımını içeren bloğun sonuna kadar görülebilir. Kapsamı bu bloğa ve bu bloktaki iç içe yerleştirilmiş tüm bloklara sınırlıdır ve ilişkili bloğu kapatan küme ayracı ile biter. Bu tür tanımlayıcılar bazen "yerel değişkenler" olarak adlandırılır.

İşlev prototipi kapsamındaki bir tanımlayıcı için bildiri dolabı veya tür Belirleyicisi, bir işlev prototipindeki (işlev bildiriminin parçası olmayan) parametre bildirimlerinin listesi içinde görünür. Kapsamı, işlev bildirimci sonunda sona erer.

Diğer kaynak dosyalarında görünür değişkenleri oluşturmak için uygun bildirimler, [depolama sınıflarında](../c-language/c-storage-classes.md)açıklanmıştır. Ancak, **statik** depolama sınıfı Belirleyicisi ile dış düzeyde belirtilen değişkenler ve işlevler yalnızca tanımlandıkları kaynak dosya içinde görünür. Tüm diğer işlevler genel olarak görünür.

## <a name="see-also"></a>Ayrıca bkz.

[Ömür, Kapsam, Görünürlük ve Bağlantı](../c-language/lifetime-scope-visibility-and-linkage.md)
