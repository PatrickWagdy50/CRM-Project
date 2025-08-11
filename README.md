<p-table
  [value]="customers"
  [(selection)]="selectedCustomers"
  dataKey="id"
  [tableStyle]="{ 'min-width': '70rem' }"
>
  <ng-template pTemplate="header">
    <tr>
      <th style="width:3rem">
        <p-checkbox
          [binary]="true"
          [ngModel]="selectedCustomers.length === customers.length"
        ></p-checkbox>
      </th>
      <th *ngFor="let col of cols">{{ col.header }}</th>
    </tr>
  </ng-template>

  <ng-template pTemplate="body" let-customer>
    <tr>
      <td>
        <p-checkbox
          [(ngModel)]="selectedCustomers"
          [value]="customer"
        ></p-checkbox>
      </td>
      <td *ngFor="let col of cols">{{ customer[col.field] }}</td>
    </tr>
  </ng-template>
</p-table>
