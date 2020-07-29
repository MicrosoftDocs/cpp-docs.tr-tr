---
title: C++'da özel durumlar ve yığını geriye doğru izleme
ms.date: 11/19/2019
ms.assetid: a1a57eae-5fc5-4c49-824f-3ce2eb8129ed
ms.openlocfilehash: e0dadc90f85caeea359fca4ed0b45868ea77177e
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221568"
---
# <a name="exceptions-and-stack-unwinding-in-c"></a>C++'da Özel Durumlar ve Yığını Geriye Doğru İzleme

C++ özel durum mekanizmasında denetim, throw deyiminden throw türünü işleyebilen ilk catch deyimine geçer. Catch ifadesine ulaşıldığında, throw ve catch deyimleri arasındaki kapsamdaki otomatik değişkenlerin hepsi *yığın geri sarma*olarak bilinen bir işlemde yok edilir. Yığın geriye doğru izleme işleminde, yürütme aşağıdaki gibi olur:

1. Denetim **`try`** ifadeye normal sıralı yürütmeye ulaşır. Bloktaki korunan bölüm **`try`** yürütülür.

1. Korunan bölümün yürütülmesi sırasında hiçbir özel durum oluşturulursa, **`catch`** bloğu izleyen yan tümceler **`try`** yürütülmez. Yürütme, **`catch`** ilişkili bloğunu izleyen son yan tümcesinden sonraki ifadede devam eder **`try`** .

1. Korunan bölümün yürütülmesi sırasında veya korunan bölümün doğrudan ya da dolaylı olarak çağırdığı herhangi bir yordam için bir özel durum oluşturulursa, işlenen tarafından oluşturulan nesneden bir özel durum nesnesi oluşturulur **`throw`** . (Bu, bir kopya oluşturucunun dahil olabileceğini gösterir.) Bu noktada, derleyici **`catch`** daha yüksek bir yürütme bağlamında oluşturulan türdeki bir özel durumu işleyebilen veya **`catch`** herhangi bir özel durum türünü işleyebilen bir işleyici için bir yan tümce arar. **`catch`** İşleyiciler, bloğundan sonra görünüşlerinin sırayla incelenir **`try`** . Uygun bir işleyici bulunmazsa, dinamik olarak kapsayan sonraki **`try`** blok incelenir. Bu işlem, en dıştaki kapsayan **`try`** blok incelenene kadar devam eder.

1. Eşleşen bir işleyici hala bulunamazsa ya da geriye doğru işlem sırasında işleyici denetimi almadan önce bir özel durum oluşursa, önceden tanımlanmış çalışma zamanı işlevi `terminate` çağrılır. Özel durum, geriye doğru izleme başlamadan önce ve bir özel durum oluştuktan sonra oluşursa, `terminate` çağrılır.

1. Eşleşen bir **`catch`** işleyici bulunursa ve değere göre yakalarsa, biçimsel parametresi özel durum nesnesi kopyalanarak başlatılır. Başvuruya göre yakalarsa, parametre özel durum nesnesine başvurmak için başlatılır. Biçimsel parametre başlatıldıktan sonra, yığını geriye doğru izleme işlemi başlar. Bu, tam olarak oluşturulmuş, ancak **`try`** işleyici ile ilişkili bloğunun başlangıcı **`catch`** ve özel durumun throw sitesi arasında tamamen oluşturulan, ancak henüz kararsız olmayan tüm otomatik nesnelerin yok edilmesini içerir. Yok etme işlemi oluşturma işleminin ters sırasıyla yapılır. **`catch`** İşleyici yürütülür ve program son işleyiciden sonra yürütmeyi sürdürür — diğer bir deyişle, işleyici olmayan ilk ifadede veya yapısıdır **`catch`** . Denetim, yalnızca bir **`catch`** **`goto`** bildirimde veya bir **`case`** deyimdeki etikette hiçbir şekilde oluşturulan özel durum aracılığıyla bir işleyici girebilir **`switch`** .

## <a name="stack-unwinding-example"></a>Yığın geriye doğru izleme örneği

Aşağıdaki örnek, bir özel durum oluştuğunda yığının nasıl kaçınılacağını gösterir. İş parçacığı üzerindeki yürütme, `C` içindeki throw deyiminden `main` içindeki catch deyimine atlar ve yol boyunca her işlevi geriye doğru alır. `Dummy` nesnelerinin oluşturulduğu ve ardından kapsam dışına çıkarken yok edildikleri sıralamaya dikkat edin. Ayrıca, catch deyimini içeren `main` haricinde, hiçbir işlevin tamamlamadığına dikkat edin. `A` işlevi `B()` için yaptığı çağrıdan, `B` işlevi de `C()` için yaptığı çağrıdan hiçbir zaman dönmez. `Dummy` işaretçisine ve ilişkili delete deyiminin tanımına ilişkin açıklamayı kaldırır ve ardından programı çalıştırırsanız, işaretçinin asla silinmediğine dikkat edin. Bu, işlevler özel durum sağlamadığında neler olabileceğini gösterir. Daha fazla bilgi için bkz. Nasıl yapılır: Özel Durumlar için Tasarım. Catch deyimi için açıklama satırı yaparsanız, işlenmemiş bir özel durum nedeniyle bir program sonlandığında ne olacağını görebilirsiniz.

```cpp
#include <string>
#include <iostream>
using namespace std;

class MyException{};
class Dummy
{
    public:
    Dummy(string s) : MyName(s) { PrintMsg("Created Dummy:"); }
    Dummy(const Dummy& other) : MyName(other.MyName){ PrintMsg("Copy created Dummy:"); }
    ~Dummy(){ PrintMsg("Destroyed Dummy:"); }
    void PrintMsg(string s) { cout << s  << MyName <<  endl; }
    string MyName;
    int level;
};

void C(Dummy d, int i)
{
    cout << "Entering FunctionC" << endl;
    d.MyName = " C";
    throw MyException();

    cout << "Exiting FunctionC" << endl;
}

void B(Dummy d, int i)
{
    cout << "Entering FunctionB" << endl;
    d.MyName = "B";
    C(d, i + 1);
    cout << "Exiting FunctionB" << endl;
}

void A(Dummy d, int i)
{
    cout << "Entering FunctionA" << endl;
    d.MyName = " A" ;
  //  Dummy* pd = new Dummy("new Dummy"); //Not exception safe!!!
    B(d, i + 1);
 //   delete pd;
    cout << "Exiting FunctionA" << endl;
}

int main()
{
    cout << "Entering main" << endl;
    try
    {
        Dummy d(" M");
        A(d,1);
    }
    catch (MyException& e)
    {
        cout << "Caught an exception of type: " << typeid(e).name() << endl;
    }

    cout << "Exiting main." << endl;
    char c;
    cin >> c;
}

/* Output:
    Entering main
    Created Dummy: M
    Copy created Dummy: M
    Entering FunctionA
    Copy created Dummy: A
    Entering FunctionB
    Copy created Dummy: B
    Entering FunctionC
    Destroyed Dummy: C
    Destroyed Dummy: B
    Destroyed Dummy: A
    Destroyed Dummy: M
    Caught an exception of type: class MyException
    Exiting main.

*/
```
