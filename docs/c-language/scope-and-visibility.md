---
description: 'Daha fazla bilgi edinin: kapsam ve görünürlük'
title: Kapsam ve Görünürlük
ms.date: 11/04/2016
helpviewer_keywords:
- scope, levels
- visibility
- file scope [C++]
ms.assetid: a019eb7c-66ed-46a7-bc9f-89a963930a56
ms.openlocfilehash: 188fbedad87e370e8b5b1e7dabc475e301ca3f4f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97292838"
---
# <a name="scope-and-visibility"></a>Kapsam ve Görünürlük

Bir tanımlayıcının "görünürlük", başvurubileceği programın ("kapsam") bölümlerini belirler. Bir tanımlayıcı görünür (yani, kullanılabilir) yalnızca "kapsamı" ile dahil olan bir programın bölümlerinde, sınırlı olabilen dosya, işlev, blok veya işlev prototipini ile sınırlı olabilecek (artan kısıtlayıcı bir şekilde) olabilir. Bir tanımlayıcının kapsamı, programın adının kullanılabileceği bölümüdür. Buna bazen "sözcük temelli kapsam" adı verilir. Dört tür kapsam vardır: işlev, dosya, blok ve işlev prototipi.

Etiketler hariç tüm tanımlayıcıların kapsamı, bildirimin gerçekleştiği düzeye göre belirlenir. Her bir kapsam türü için aşağıdaki kurallar, bir program içindeki tanımlayıcıların görünürlüğünü yönetir:

Dosya kapsamı dosya kapsamına sahip bir tanımlayıcı için bildirimci veya tür Belirleyicisi, herhangi bir blok veya parametre listesi dışında görünür ve bildiriminden sonra çeviri biriminde herhangi bir yerden erişilebilir olur. Dosya kapsamına sahip tanımlayıcı adları genellikle "Global" veya "External" olarak adlandırılır. Genel tanımlayıcının kapsamı, tanım veya bildiriminin başlangıcında başlar ve çeviri biriminin sonunda sonlanır.

İşlev kapsamı bir etiket işlev kapsamına sahip tek tanımlayıcı türüdür. Bir etiket, bir ifadede kullanımı tarafından örtük olarak bildirilmiştir. Etiket adları bir işlev içinde benzersiz olmalıdır. (Etiketler ve etiket adları hakkında daha fazla bilgi için bkz. [goto ve etiketli deyimler](../c-language/goto-and-labeled-statements-c.md).)

Blok kapsamı blok kapsamına sahip bir tanımlayıcı için bildirimci veya tür Belirleyicisi, bir blok içinde veya bir işlev tanımında biçimsel parametre bildirimleri listesi içinde görüntülenir. Yalnızca kendi bildirimi veya tanımı, bildirimini veya tanımını içeren bloğun sonuna kadar görülebilir. Kapsamı bu bloğa ve bu bloktaki iç içe yerleştirilmiş tüm bloklara sınırlıdır ve ilişkili bloğu kapatan küme ayracı ile biter. Bu tür tanımlayıcılar bazen "yerel değişkenler" olarak adlandırılır.

İşlev prototipi kapsamındaki bir tanımlayıcı için bildiri dolabı veya tür Belirleyicisi, bir işlev prototipindeki (işlev bildiriminin parçası olmayan) parametre bildirimlerinin listesi içinde görünür. Kapsamı, işlev bildirimci sonunda sona erer.

Diğer kaynak dosyalarında görünür değişkenleri oluşturmak için uygun bildirimler, [depolama sınıflarında](../c-language/c-storage-classes.md)açıklanmıştır. Ancak, dış düzeyde, **`static`** depolama sınıfı belirticisiyle belirtilen değişkenler ve işlevler yalnızca tanımlandıkları kaynak dosya içinde görünür. Tüm diğer işlevler genel olarak görünür.

## <a name="see-also"></a>Ayrıca bkz.

[Ömür, kapsam, görünürlük ve bağlantı](../c-language/lifetime-scope-visibility-and-linkage.md)
