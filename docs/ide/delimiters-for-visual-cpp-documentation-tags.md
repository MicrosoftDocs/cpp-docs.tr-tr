---
title: Visual C++ belge etiketleri için sınırlayıcılar | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- XML documentation, delimiters
ms.assetid: debfbdd9-63fa-4c58-a18e-a4d203d241d7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8fe65dfec3befa15ffebde3d074081ee11364f4d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="delimiters-for-visual-c-documentation-tags"></a>Visual C++ Belge Etiketleri için Sınırlayıcılar
Belge etiketleri kullanılmasını burada belgelerine yorum başlar ve biter derleyici belirtmek sınırlayıcıları gerektirir.  
  
 XML belgeleri etiketlerle sınırlayıcıları şu tür kullanabilirsiniz:  
  
 `///`  
 Bu belge örneklerde gösterilen ve Visual C++ proje şablonları tarafından kullanılan formdur.  
  
 `/** */`  
 Bunlar çok satırlı sınırlayıcı olarak kullanılır.  
  
 Var olan bazı biçimlendirme kuralları kullanırken `/** */` sınırlayıcılar:  
  
-   İçeren satırı için `/**` kalan satırının satır boşluk ise sınırlayıcı açıklamaları için işlenmedi. İlk karakteri boşluk ise, bu boşluk karakteri dikkate alınmaz ve satır kalan işlenir. Aksi takdirde satırından sonra tüm metnin `/**` sınırlayıcı yorum bir parçası olarak işlenir.  
  
-   İçeren satırı için `*/` varsa yalnızca boşluk kadar sınırlayıcı `*/` sınırlayıcısı, o satırdaki göz ardı edilir. Aksi takdirde kadar satırındaki metin `*/` sınırlayıcı aşağıdaki maddede açıklandığı desen eşleştirme kuralları tabi yorum bir parçası olarak işlenir.  
  
-   İle başlayan bir sonraki satırların için `/**` sınırlayıcısı, derleyici, isteğe bağlı boşluk ve bir yıldız işareti oluşan her satırın başındaki genel bir desen arar (`*`), ardından daha fazla isteğe bağlı boşluk. Derleyici her satırın başındaki ortak bir karakter kümesi bulursa, sonra tüm çizgiler için bu deseni yoksayacak `/**` sınırlayıcısı, kadar ve muhtemelen içeren satırı dahil `*/` sınırlayıcısı.  
  
 Bazı örnekler:  
  
-   Yalnızca nasıl işleneceğini aşağıdaki açıklama ile başlayan satırı parçasıdır `<summary>`. Aşağıdaki iki etiket biçimlerini aynı açıklamaları üretir:  
  
    ```  
    /**  
    <summary>text</summary>   
    */  
    /** <summary>text</summary> */  
    ```  
  
-   Derleyici bir desenini uygular "*" ikinci ve üçüncü satır başında yoksaymak için.  
  
    ```  
    /**  
     * <summary>  
     *  text </summary>*/  
    ```  
  
-   İkinci satırda bir yıldız işareti olduğundan derleyici hiçbir düzeni Bu açıklamada bulur. Bu nedenle, tüm metin ikinci ve üçüncü satırlarındaki yukarı kasa `*/`, yorum bir parçası olarak işlenir.  
  
    ```  
    /**  
     * <summary>  
       text </summary>*/  
    ```  
  
-   Derleyici hiçbir düzeni iki nedenden dolayı bu açıklamada bulur. İlk olarak, tutarlı bir yıldız işareti önce boşluk sayısı ile başlayan hiçbir satır vardır. İkinci olarak, beşinci satır alanları eşleşmiyor bir sekme ile başlar. Bu nedenle, tüm metni kadar ikinci satırında `*/` yorum bir parçası olarak işlenir.  
  
    ```  
    /**  
      * <summary>  
      * text   
     *  text2  
       *  </summary>  
    */  
    ```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [XML Belgeleri](../ide/xml-documentation-visual-cpp.md)