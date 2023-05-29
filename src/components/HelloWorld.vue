<script setup>
import { ref } from "vue";
import jsPDF from "jspdf";
import autoTable from "jspdf-autotable";
const tableHeader = [
  { title: "Name" },
  { title: "Launch Date" },
  { title: "Matured Date" },
  { title: "No Of Share" },
  {
    title: "No Of Sold Share",
  },
  {
    title: "Par Share Amount",
  },
  {
    title: "Required Amount",
  },
  {
    title: "My Invested amount",
  },
  { title: "My No Of Share" },
  { title: "Total Earnning" },
  { title: "Overall Earning" },
];
const tabledata = [
  {
    id: 13,
    investment_transactions: [
      {
        id: 5,
        investor: {
          id: 18,
          username: "minhajs",
          first_name: "",
          last_name: "",
          designation: null,
          email: "minhajsorder8205@gmail.com",
          mobile: null,
          profile_image: null,
          profile_image_thumbnail: null,
          user_type: "investor",
        },
        transaction_amount: 10000,
        no_of_share: 4,
        transaction_date: "2023-05-28 15:54:08",
        created_at: "2023-05-28 15:54:08",
        updated_at: "2023-05-28 15:54:08",
        investment: 13,
        created_by: 18,
        updated_by: null,
      },
    ],
    project_story: null,
    project_faqs: [],
    project_slider_images: [],
    created_by: {
      id: 4,
      username: "accountant",
      first_name: "Demo A First Name",
      last_name: "Last Name",
      designation: null,
      email: "accountant@examle.com",
      mobile: null,
      profile_image: null,
      profile_image_thumbnail: null,
      user_type: "accountant",
    },
    updated_by: null,
    department: {
      id: 1,
      children: [],
      created_by: null,
      updated_by: null,
      name: "Department 1",
      description: "Department 1",
      created_at: "2023-05-23 04:57:55",
      updated_at: "2023-05-23 04:57:55",
      parent: null,
      root: "",
    },
    name: "Electronics Charger",
    description: "test",
    is_featured: false,
    is_published: false,
    status: "booked",
    investment_start_date: "2023-05-28",
    investment_end_date: "2023-06-30",
    launch_date: "2023-05-28",
    matured_date: "2024-05-22",
    project_cover_image:
      "http://45.94.209.101:5107/media/project_cover_image/placeholder_image.png",
    project_cover_image_thumbnail:
      "http://45.94.209.101:5107/media/project_cover_image_thumbnail/thumbnail_placeholder_image.png",
    profit_calculation_type: "installment",
    project_value: 0,
    overall_earning_amount: 0,
    required_investment_amount: 0,
    par_share_amount: 2500,
    no_of_share: 4,
    created_at: "2023-05-28 15:46:02",
    updated_at: "2023-05-28 15:54:38",
    old_version: null,
    invested_amount: 10000,
    no_of_share_sold: 4,
    investor_count: 1,
    my_total_invested_amount: 10000,
    my_total_no_of_share: 4,
    earn_from_this_project: null,
    product_profit: 2000,
    product_offered_price: 12000,
  },
];

const handlePdfDownload = () => {
  const doc = new jsPDF();

  autoTable(doc, {
    body: [
      [
        {
          content: "Company brand",
          styles: {
            halign: "left",
            fontSize: 20,
            textColor: "#ffffff",
          },
        },
        {
          content: "Invoice",
          styles: {
            halign: "right",
            fontSize: 20,
            textColor: "#ffffff",
          },
        },
      ],
    ],
    theme: "plain",
    styles: {
      fillColor: "#3366ff",
    },
  });

  autoTable(doc, {
    body: [
      [
        {
          content:
            "Reference: #INV0001" +
            "\nDate: 2022-01-27" +
            "\nInvoice number: 123456",
          styles: {
            halign: "right",
          },
        },
      ],
    ],
    theme: "plain",
  });

  autoTable(doc, {
    body: [
      [
        {
          content:
            "Billed to:" +
            "\nJohn Doe" +
            "\nBilling Address line 1" +
            "\nBilling Address line 2" +
            "\nZip code - City" +
            "\nCountry",
          styles: {
            halign: "left",
          },
        },
        {
          content:
            "Shipping address:" +
            "\nJohn Doe" +
            "\nShipping Address line 1" +
            "\nShipping Address line 2" +
            "\nZip code - City" +
            "\nCountry",
          styles: {
            halign: "left",
          },
        },
        {
          content:
            "From:" +
            "\nCompany name" +
            "\nShipping Address line 1" +
            "\nShipping Address line 2" +
            "\nZip code - City" +
            "\nCountry",
          styles: {
            halign: "right",
          },
        },
      ],
    ],
    theme: "plain",
  });

  autoTable(doc, {
    body: [
      [
        {
          content: "Amount due:",
          styles: {
            halign: "right",
            fontSize: 14,
          },
        },
      ],
      [
        {
          content: "$4000",
          styles: {
            halign: "right",
            fontSize: 20,
            textColor: "#3366ff",
          },
        },
      ],
      [
        {
          content: "Due date: 2022-02-01",
          styles: {
            halign: "right",
          },
        },
      ],
    ],
    theme: "plain",
  });

  autoTable(doc, {
    body: [
      [
        {
          content: "Products & Services",
          styles: {
            halign: "left",
            fontSize: 14,
          },
        },
      ],
    ],
    theme: "plain",
  });

  autoTable(doc, {
    //     const tableHeader = [
    //   { title: "Name" },
    //   { title: "Launch Date" },
    //   { title: "Matured Date" },
    //   { title: "No Of Share" },
    //   {
    //     title: "No Of Sold Share",
    //   },
    //   {
    //     title: "Par Share Amount",
    //   },
    //   {
    //     title: "Required Amount",
    //   },
    //   {
    //     title: "My Invested amount",
    //   },
    //   { title: "My No Of Share" },
    //   { title: "Total Earnning" },
    //   { title: "Overall Earning" },
    // ];
    // header:[[]],
    // body:[[]],
    head: [tableHeader?.map((item) => item.title)],
    body: [
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
      ["Product or service name", "Category", "2", "$450", "$50", "$1000"],
    ],
    // html: "#table",
    theme: "striped",
    headStyles: {
      fillColor: "#343a40",
    },
  });

  autoTable(doc, {
    body: [
      [
        {
          content: "Subtotal:",
          styles: {
            halign: "right",
          },
        },
        {
          content: "$3600",
          styles: {
            halign: "right",
          },
        },
      ],
      [
        {
          content: "Total tax:",
          styles: {
            halign: "right",
          },
        },
        {
          content: "$400",
          styles: {
            halign: "right",
          },
        },
      ],
      [
        {
          content: "Total amount:",
          styles: {
            halign: "right",
          },
        },
        {
          content: "$4000",
          styles: {
            halign: "right",
          },
        },
      ],
    ],
    theme: "plain",
  });

  autoTable(doc, {
    body: [
      [
        {
          content: "Terms & notes",
          styles: {
            halign: "left",
            fontSize: 14,
          },
        },
      ],
      [
        {
          content:
            "orem ipsum dolor sit amet consectetur adipisicing elit. Maxime mollitia" +
            "molestiae quas vel sint commodi repudiandae consequuntur voluptatum laborum" +
            "numquam blanditiis harum quisquam eius sed odit fugiat iusto fuga praesentium",
          styles: {
            halign: "left",
          },
        },
      ],
    ],
    theme: "plain",
  });

  autoTable(doc, {
    body: [
      [
        {
          content: "Footer",
          styles: {
            halign: "center",
          },
        },
      ],
    ],
    theme: "plain",
  });

  //  page number 
  const pageCount = doc.internal.getNumberOfPages();
  doc.setFontSize(10);
  for (var i = 1; i <= pageCount; i++) {
    doc.setPage(i);
    doc.text(
      190,
      285,
      doc.internal.getCurrentPageInfo().pageNumber + "/" + pageCount
    );
  }


  return doc.save("invoice");
};

defineProps({
  msg: String,
});

const count = ref(0);
</script>

<template>
  <h1>{{ msg }}</h1>

  <div class="card">
    <button type="button" @click="count++"
    style="margin-right:10px ;"
    >count is {{ count }}</button>
    <button type="button" @click="handlePdfDownload">Download</button>
    <p>
      Edit
      <code>components/HelloWorld.vue</code> to test HMR
    </p>
  </div>

  <section>
    <table id="table">
      <thead>
        <!-- tableHeader array is defined in the script section -->
        <tr>
          <th v-for="row in tableHeader" :key="row">
            {{ row.title }}
          </th>
        </tr>
      </thead>
      <tbody>
        <!-- tableData array is defined in the script section -->
        <tr>
          <td v-for="row in tableData" :key="row"></td>
        </tr>
      </tbody>
    </table>
  </section>
</template>

<style scoped>
.read-the-docs {
  color: #888;
}
</style>
