# Asyntaskjsonparsingadapter
jsonadapter
public class ContactAdapter extends ArrayAdapter<String> {
    ArrayList<ContactBean> result;
    Context context;

    public ContactAdapter(Context context, int resource, ArrayList response) {
        super(context, resource, response);
        result=response;
        this.context=context;
    }


    public View getView(int position,View view,ViewGroup parent) {
        LayoutInflater inflater= (LayoutInflater) context.getSystemService(context.LAYOUT_INFLATER_SERVICE);
        View rowView=inflater.inflate(R.layout.list_item, null,true);
        TextView txtName= (TextView) rowView.findViewById(R.id.name);
        TextView txtemail= (TextView) rowView.findViewById(R.id.email);
        TextView txtMobile= (TextView) rowView.findViewById(R.id.gender);
        TextView mobileone= (TextView) rowView.findViewById(R.id.mobile1);
        TextView mobiletwo= (TextView) rowView.findViewById(R.id.mobile2);
        TextView mobilethree= (TextView) rowView.findViewById(R.id.mobile3);



        Log.e("Result", result.toString());

        ContactBean cbObj=result.get(position);
        txtName.setText("Name :"+cbObj.getName());
        txtemail.setText("Email :"+cbObj.getEmail());
        txtMobile.setText("Gender :" + cbObj.getGender());
        mobileone.setText("mobilenumber :" + cbObj.getMobile());
        mobiletwo.setText("officenumber :" + cbObj.getOffice());
        mobilethree.setText("home :" + cbObj.getHome());
       /* //HashMap<String,String> resultMap=result.get(position);
        txtName.setText("Name :"+resultMap.get("Name"));
        txtemail.setText("Email :"+resultMap.get("Email"));
        txtMobile.setText("Gender :"+resultMap.get("Gender"));*/






        return rowView;

    };
}
